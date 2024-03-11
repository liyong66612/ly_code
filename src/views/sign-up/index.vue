<script lang="ts" setup>
import { User, Lock, Key, Picture, Loading } from "@element-plus/icons-vue"
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
        <form class="card card-md" action="./" method="get" autocomplete="off" novalidate>
          <div class="card-body">
            <h2 class="card-title text-center mb-4">Create new account</h2>
            <div class="mb-3">
              <label class="form-label">Name</label>
              <el-input type="text" tabindex="1" :prefix-icon="User" size="large" />
            </div>
            <div class="mb-3">
              <label class="form-label">Password</label>
              <el-input type="password" tabindex="2" size="large" show-password :prefix-icon="Lock" />
            </div>
            <div class="mb-3">
              <label class="form-label">rewrite Password</label>
              <div class="input-group input-group-flat">
                <el-input type="password" tabindex="2" size="large" show-password :prefix-icon="Lock" />
              </div>
            </div>
            <div class="mb-3">
              <label class="form-check">
                <input type="checkbox" class="form-check-input" />
                <span class="form-check-label"
                  >Agree the <a href="./terms-of-service.html" tabindex="-1">terms and policy</a>.</span
                >
              </label>
            </div>
            <div class="form-footer">
              <el-button color="#0054A6" class="w-100" type="primary" size="large">Create new account</el-button>
            </div>
          </div>
        </form>
        <div class="text-center text-secondary mt-3">
          Already have account? <router-link to="/login">Sign in</router-link>
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
