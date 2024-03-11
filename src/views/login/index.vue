<script lang="ts" setup>
import { reactive, ref } from "vue"
import { useRouter } from "vue-router"
import { useUserStore } from "@/store/modules/user"
import { type LoginRequestData } from "@/api/login/types/login"
import { getLoginCodeApi } from "@/api/login"
import { type FormInstance, type FormRules } from "element-plus"
import { User, Lock, Key, Picture, Loading } from "@element-plus/icons-vue"
import { useFocus } from "./hooks/useFocus"
const { isFocus, handleBlur, handleFocus } = useFocus()

const labelPosition = ref("top")
const router = useRouter()
/** 登录表单元素的引用 */
const loginFormRef = ref<FormInstance | null>(null)
/** 登录表单数据 */
const loginFormData: LoginRequestData = reactive({
  username: "admin",
  password: "123456",
  rememberPas: ""
})
/** 登录按钮 Loading */
const loading = ref(false)
/** 验证码图片 URL */
const codeUrl = ref("")
/** 登录表单校验规则 */
const loginFormRules: FormRules = {
  username: [{ required: true, message: "请输入用户名", trigger: "blur" }],
  password: [
    { required: true, message: "请输入密码", trigger: "blur" },
    { min: 8, max: 16, message: "长度在 8 到 16 个字符", trigger: "blur" }
  ],
  code: [{ required: true, message: "请输入验证码", trigger: "blur" }]
}
/** 登录逻辑 */
const handleLogin = () => {
  loginFormRef.value?.validate((valid: boolean, fields) => {
    if (valid) {
      loading.value = true
      useUserStore()
        .login(loginFormData)
        .then(() => {
          router.push({ path: "/" })
        })
        .catch(() => {
          createCode()
          loginFormData.password = ""
        })
        .finally(() => {
          loading.value = false
        })
    } else {
      console.error("表单校验不通过", fields)
    }
  })
}
/** 创建验证码 */
const createCode = () => {
  // 先清空验证码的输入
  loginFormData.code = ""
  // 获取验证码
  codeUrl.value = ""
  getLoginCodeApi().then((res) => {
    codeUrl.value = res.data
  })
}

/** 初始化验证码 */
createCode()
</script>

<template>
  <div class="d-flex flex-column h-100">
    <div class="page page-center">
      <div class="container container-tight py-4">
        <div class="text-center mb-4">
          <a href="." class="navbar-brand navbar-brand-autodark">
            <img src="@/assets/login/logo.svg" width="100" height="32" alt="Tabler" class="navbar-brand-image" />
          </a>
        </div>
        <div class="card card-md">
          <div class="card-body">
            <h2 class="h2 text-center mb-4">登录</h2>
            <el-form
              ref="loginFormRef"
              :label-position="labelPosition"
              :model="loginFormData"
              :rules="loginFormRules"
              @keyup.enter="handleLogin"
            >
              <el-form-item prop="username" label="用户名">
                <el-input
                  v-model.trim="loginFormData.username"
                  type="text"
                  tabindex="1"
                  :prefix-icon="User"
                  size="large"
                />
              </el-form-item>
              <el-form-item prop="password" label="密码">
                <el-input
                  v-model.trim="loginFormData.password"
                  placeholder="密码"
                  type="password"
                  tabindex="2"
                  :prefix-icon="Lock"
                  size="large"
                  show-password
                  @blur="handleBlur"
                  @focus="handleFocus"
                />
              </el-form-item>
              <el-form-item prop="code">
                <el-input
                  v-model.trim="loginFormData.code"
                  placeholder="验证码"
                  type="text"
                  tabindex="3"
                  :prefix-icon="Key"
                  maxlength="7"
                  size="large"
                >
                  <template #append>
                    <el-image :src="codeUrl" @click="createCode" draggable="false">
                      <template #placeholder>
                        <el-icon>
                          <Picture />
                        </el-icon>
                      </template>
                      <template #error>
                        <el-icon>
                          <Loading />
                        </el-icon>
                      </template>
                    </el-image>
                  </template>
                </el-input>
              </el-form-item>
              <!-- <el-form-item prop="code">
                <el-input
                  v-model.trim="loginFormData.code"
                  placeholder="验证码"
                  type="text"
                  tabindex="3"
                  :prefix-icon="Key"
                  maxlength="7"
                  size="large"
                >
                  <template #append>
                    <el-image :src="codeUrl" @click="createCode" draggable="false">
                      <template #placeholder>
                        <el-icon>
                          <Picture />
                        </el-icon>
                      </template>
                      <template #error>
                        <el-icon>
                          <Loading />
                        </el-icon>
                      </template>
                    </el-image>
                  </template>
                </el-input>
              </el-form-item> -->
              <div class="mb-2">
                <label class="form-check">
                  <input type="checkbox" class="form-check-input" />
                  <span class="form-check-label">记住密码</span>
                </label>
              </div>
              <el-button
                color="#0054A6"
                class="w-100"
                :loading="loading"
                type="primary"
                size="large"
                @click.prevent="handleLogin"
                >登 录</el-button
              >
            </el-form>
          </div>
        </div>
        <div class="text-center text-secondary mt-3">
          点击此处注册账号
          <router-link to="/sign-up">Sign up</router-link>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.navbar-brand-image {
  height: 3rem !important;
}
</style>
