<template>
  <div class="auth">
      <div class="form">
        <h1 class="h3 mb-3 fw-normal">Пожалуйста, войдите в систему</h1>

        <div class="form-floating">
          <input type="email" class="form-control" v-model="this.email" id="floatingInput" placeholder="name@example.com">
          <label for="floatingInput">Е-mail</label>
        </div>
        <div class="form-floating">
          <input type="password" class="form-control" v-model="this.password" id="floatingPassword" placeholder="Password">
          <label for="floatingPassword">Пароль</label>
        </div>

        <div class="form-floating">
          <a @click="this.$emit('switchLayout', '')" class="icon-link">Зарегистрироваться ></a>
        </div>

        <button class="btn btn-primary w-100 py-2" @click="submit">Войти</button>
      </div>
  </div>
</template>

<script>
import * as Api from '../assets/Api.js'

export default {
  name: 'AuthPage',
  data() {
    return{
      email: '',
      password: ''
    }
  },
  methods: {
    submit() {
      this.$emit('user_id', Api.authUser(this.email, this.password))
    }
  },
}
</script>

<style scoped>
</style>