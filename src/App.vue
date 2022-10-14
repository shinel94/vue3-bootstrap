
<template>

  <dashboard-component v-if="isLogin" @logout="logout"/>
  <Login v-else="isLogin" @login="login"/>
</template>

<script setup lang="ts">
import { defineAsyncComponent, ref } from 'vue';
import Login from './components/Login.vue';
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup

const isLogin = ref(false)

const login = () => {
  isLogin.value = true
}

const logout = () => {
  isLogin.value = false
}

const DashboardComponent = defineAsyncComponent(() => import('./components/Dashboard.vue'))

</script>


<style scoped lang="scss">
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  &:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
