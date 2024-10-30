<template>
  <v-app>
    <v-app-bar color="primary" density="compact">
      <v-app-bar-title class="d-flex align-center">
        <img src="/LunarShield-logo.svg" alt="LunarShield" height="32" class="me-2" />
        LunarShield
      </v-app-bar-title>

      <v-spacer></v-spacer>

      <v-btn variant="text">产品</v-btn>
      <v-btn variant="text">行业信息</v-btn>
      <v-btn variant="text">相关技术</v-btn>
      <v-btn @click="loginDialog = true">登录</v-btn>
    </v-app-bar>

    <v-main>
      <v-container>
        <!-- Hero Section -->
        <v-row class="my-12">
          <v-col cols="12" class="text-center">
            <h1 class="text-h2 mb-6">守月科技</h1>
            <p class="text-h5">创新技术解决方案</p>
          </v-col>
        </v-row>

        <!-- Download Section -->
        <v-row>
          <v-col cols="12" md="6" class="text-center">
            <QRCode 
              title="安卓下载"
              qrImage="/android-qr.png"
            />
          </v-col>
          <v-col cols="12" md="6" class="text-center">
            <QRCode 
              title="苹果下载"
              qrImage="/ios-qr.png"
            />
          </v-col>
        </v-row>

        <!-- Contact Section -->
        <v-row class="mt-12">
          <v-col cols="12">
            <v-card>
              <v-card-title>联系地址</v-card-title>
              <v-card-text>
                <p class="text-body-1">深圳市守月科技有限公司</p>
                <p class="text-body-1">深圳市宝安区航城街道黄麻布社区簕竹角坚鼎科技园1栋厂房2层</p>
                <p class="text-body-1">lunarshied@foxmail.com</p>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>

    <!-- Login Dialog -->
    <v-dialog v-model="loginDialog" max-width="400">
      <v-card>
        <v-card-title>登录</v-card-title>
        <v-card-text>
          <v-form>
            <v-text-field
              v-model="username"
              label="用户名"
              required
            ></v-text-field>
            <v-text-field
              v-model="password"
              label="密码"
              type="password"
              required
            ></v-text-field>
          </v-form>
          <div class="text-caption mt-2">
            还没有账号？ <a href="#" @click="loginDialog = false">立即注册</a>
          </div>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="primary" @click="loginDialog = false">登录</v-btn>
          <v-btn color="grey" @click="loginDialog = false">取消</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-app>
</template>

<script setup>
import { ref } from 'vue'
import QRCode from './components/QRCode.vue'

const loginDialog = ref(false)
const username = ref('')
const password = ref('')
</script>

<style scoped>
.qr-placeholder {
  border: 2px dashed #ccc;
  border-radius: 8px;
}
</style>