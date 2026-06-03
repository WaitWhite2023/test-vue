<script setup lang="ts">
import { ref } from 'vue'

const username = ref('')
const password = ref('')
const rememberMe = ref(false)

function handleLogin() {
  console.log('登录信息：', {
    username: username.value,
    password: password.value,
    rememberMe: rememberMe.value,
  })
}
</script>

<template>
  <div class="login-container">
    <div class="login-box">
      <h1 class="login-title">欢迎登录</h1>
      <p class="login-subtitle">请输入您的账号和密码</p>

      <form class="login-form" @submit.prevent="handleLogin">
        <div class="form-group">
          <label for="username">用户名</label>
          <input
            id="username"
            v-model="username"
            type="text"
            placeholder="请输入用户名"
            required
          />
        </div>

        <div class="form-group">
          <label for="password">密码</label>
          <input
            id="password"
            v-model="password"
            type="password"
            placeholder="请输入密码"
            required
          />
        </div>

        <div class="form-options">
          <label class="remember">
            <input v-model="rememberMe" type="checkbox" />
            <span>记住我</span>
          </label>
          <a href="#" class="forgot">忘记密码？</a>
        </div>

        <button type="submit" class="login-btn">登录</button>
      </form>

      <div class="login-footer">
        还没有账号？<a href="#">立即注册</a>
      </div>
    </div>
  </div>
</template>

<style scoped>
.login-container {
  min-height: 100svh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 20px;
  background: linear-gradient(135deg, var(--bg) 0%, var(--code-bg) 100%);
}

.login-box {
  width: 100%;
  max-width: 400px;
  padding: 40px 32px;
  border-radius: 16px;
  background: var(--bg);
  border: 1px solid var(--border);
  box-shadow: var(--shadow);
}

.login-title {
  font-size: 28px;
  font-weight: 600;
  color: var(--text-h);
  text-align: center;
  margin: 0 0 8px;
  letter-spacing: -0.5px;
}

.login-subtitle {
  font-size: 15px;
  color: var(--text);
  text-align: center;
  margin: 0 0 28px;
}

.login-form {
  display: flex;
  flex-direction: column;
  gap: 18px;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 6px;
}

.form-group label {
  font-size: 14px;
  font-weight: 500;
  color: var(--text-h);
}

.form-group input {
  padding: 12px 14px;
  font-size: 15px;
  border: 1px solid var(--border);
  border-radius: 8px;
  background: var(--bg);
  color: var(--text-h);
  transition: border-color 0.2s, box-shadow 0.2s;
  font-family: inherit;
}

.form-group input::placeholder {
  color: var(--text);
  opacity: 0.6;
}

.form-group input:focus {
  outline: none;
  border-color: var(--accent-border);
  box-shadow: 0 0 0 3px var(--accent-bg);
}

.form-options {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-size: 14px;
}

.remember {
  display: flex;
  align-items: center;
  gap: 6px;
  cursor: pointer;
  color: var(--text);
}

.remember input[type='checkbox'] {
  width: 16px;
  height: 16px;
  accent-color: var(--accent);
  cursor: pointer;
}

.forgot {
  color: var(--accent);
  text-decoration: none;
  transition: opacity 0.2s;
}

.forgot:hover {
  opacity: 0.8;
  text-decoration: underline;
}

.login-btn {
  padding: 12px;
  font-size: 16px;
  font-weight: 500;
  color: #fff;
  background: var(--accent);
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: transform 0.15s, opacity 0.2s;
  font-family: inherit;
}

.login-btn:hover {
  opacity: 0.9;
}

.login-btn:active {
  transform: scale(0.98);
}

.login-footer {
  margin-top: 24px;
  text-align: center;
  font-size: 14px;
  color: var(--text);
}

.login-footer a {
  color: var(--accent);
  text-decoration: none;
  font-weight: 500;
}

.login-footer a:hover {
  text-decoration: underline;
}
</style>
