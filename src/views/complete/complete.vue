<script lang="ts" setup>
import { Check } from "@element-plus/icons-vue"
import { ref } from "vue"
const datevalue = ref({})
const radio = ref({})
</script>
<template>
  <div class="page-wrapper">
    <div class="page-body">
      <div class="container-xl">
        <div class="row row-deck row-cards">
          <div class="col-12">
            <div class="card-body">
              <ul class="steps steps-green steps-counter my-4">
                <li class="step-item">填写信息</li>
                <li class="step-item active">提交登记</li>
              </ul>
            </div>
          </div>
          <div class="col-12">
            <div style="margin: auto; justify-content: center">
              <div class="col text-center">
                <el-icon color="green" size="50px"><Check /></el-icon>
              </div>
              <div class="col text-center"><p style="font-size: large">信息提交成功</p></div>
            </div>
          </div>
          <div style="width: 100%; height: 20px">
            <p style="font-size: large">邀约人信息</p>
          </div>
          <div class="col-12">
            <div class="card">
              <div class="card-body">
                <div class="row pb-2">
                  <div class="col text-center">姓名</div>
                  <div class="col text-center">XXX</div>
                </div>
                <div class="row py-2">
                  <div class="col text-center">手机号码</div>
                  <div class="col text-center">130XXXXXXXXX</div>
                </div>
                <div class="row py-2">
                  <div class="col text-center">楼层</div>
                  <div class="col text-center">18楼</div>
                </div>
              </div>
            </div>
          </div>
          <div style="width: 100%; height: 20px">
            <p style="font-size: large">访客信息</p>
          </div>
          <div class="col-12">
            <div class="card">
              <div class="card-body">
                <div class="row pb-2">
                  <div class="col text-center">姓名</div>
                  <div class="col text-center">XXX</div>
                </div>
                <div class="row py-2">
                  <div class="col text-center">手机号码</div>
                  <div class="col text-center">130XXXXXXXXX</div>
                </div>
                <div class="row py-2">
                  <div class="col text-center">预约时间</div>
                  <div class="col text-center">xxxxxxx</div>
                </div>
                <div class="row py-2">
                  <div class="col text-center">来访目的</div>
                  <div class="col text-center">合作</div>
                </div>
                <div class="row py-2">
                  <div class="col text-center">身份证号</div>
                  <div class="col text-center">xxxxxxxxxxxxxxxxxx</div>
                </div>
                <div class="row py-2">
                  <div class="col text-center">车牌号</div>
                  <div class="col text-center">粤Bxxxxx</div>
                </div>
                <div class="row py-2">
                  <div class="col text-center">来访状态</div>
                  <div class="col text-center">
                    <el-radio-group v-model="radio">
                      <el-radio :value="3">已到访</el-radio>
                      <el-radio :value="6">未到访</el-radio>
                    </el-radio-group>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-12" />
          <div class="row g-2 align-items-center" align="center">
            <!-- <div class="col"> -->
            <router-link to="/">
              <el-button type="success" size="large" round>返回首页</el-button>
            </router-link>
            <!-- </div> -->
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
