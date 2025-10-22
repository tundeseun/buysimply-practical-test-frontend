<script setup>
import { reactive, ref } from 'vue'
const form = reactive({ email: '', password: '', remember: false })
const errors = reactive({ email: '', password: '' })
const showPassword = ref(false)
const loading = ref(false)

function validate(){
  errors.email = form.email ? '' : 'Email is required'
  errors.password = form.password ? '' : 'Password is required'
  return !errors.email && !errors.password
}
async function signin(){
  if(!validate()) return
  loading.value = true
  await new Promise(r => setTimeout(r, 700))
  loading.value = false
  alert('Signed in! (stub)')
}
</script>
<template>
  <div class="left">
    <div class="brand">
      <img src="/src/assets/logo.svg" alt="Team Achieve" />
      <div class="title">Team Achieve</div>
    </div>
    <div class="hero">
      <img src="/src/assets/hero.svg" alt="Happy team" />
    </div>
    <div class="caption">
      <div class="name">Team Achieve</div>
      <div class="tag">Your perfect solution for funding your desires</div>
    </div>
  </div>

  <div class="right">
    <div class="form-title">Welcome Back</div>
    <div class="form-sub">Enter your email address and password to access your account.</div>

    <form class="form" @submit.prevent="signin">
      <div>
        <div class="label">Email Address <span class="req">*</span></div>
        <input class="input" type="email" placeholder="Enter your email" v-model="form.email" />
        <div class="notice" :class="{show: errors.email}">{{ errors.email }}</div>
      </div>

      <div class="helper">
        <div class="label">Password <span class="req">*</span></div>
        <input class="input" :type="showPassword ? 'text' : 'password'" placeholder="Enter your password" v-model="form.password" />
        <button type="button" class="toggle" @click="showPassword = !showPassword">{{ showPassword ? '🙈' : '👁️' }}</button>
        <div class="notice" :class="{show: errors.password}">{{ errors.password }}</div>
      </div>

      <div class="row">
        <label class="checkbox">
          <input type="checkbox" v-model="form.remember" />
          <span>Remember me</span>
        </label>
        <a href="#">Forgot Password?</a>
      </div>

      <button class="btn" :disabled="loading" type="submit">{{ loading ? 'Signing in…' : 'Sign in' }}</button>
      <div class="bottom">Don’t have an account? <a href="#">Sign up</a></div>
    </form>

    <footer><p class="credit">© {{ new Date().getFullYear() }} Team Achieve</p></footer>
  </div>
</template>
