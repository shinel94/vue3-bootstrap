<template>
  <main class="form-signin">
    <form>
      <img
        class="mb-4"
        src="../assets/logo.png"
        alt=""
        height="100"
      />
      <h1 class="h3 mb-3 fw-normal">Please sign in</h1>

      <div class="form-floating">
        <input
          type="email"
          class="form-control"
          id="floatingInput"
          placeholder="name@example.com"
          v-model="id"
        />
        <label for="floatingInput">Email address</label>
      </div>
      <div class="form-floating">
        <input
          type="password"
          class="form-control"
          id="floatingPassword"
          placeholder="Password"
          v-model="pwd"
        />
        <label for="floatingPassword">Password</label>
      </div>

      <div class="checkbox mb-3">
        <label>
          <input type="checkbox" value="remember-me" /> Remember me
        </label>
      </div>
      <button class="w-100 btn btn-lg btn-primary" type="submit" @click="login">
        Sign in
      </button>
    </form>
  </main>
</template>

<script setup lang="ts">
import "bootstrap/dist/css/bootstrap.min.css";
import { ref, defineEmits } from "vue";

const id = ref("")
const pwd = ref("")

const emit = defineEmits(['login'])

const login = (e: Event) => {
    e.preventDefault()
    alert(`${id.value} ${pwd.value}`);
    emit('login');
}

</script>

<style scoped lang="scss">
.form-signin {
    margin: 5rem auto;
    width: 30rem;
}
</style>
