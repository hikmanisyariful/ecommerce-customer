<template>
  <form class="register-manual" @submit.prevent="registerProcess">
    <label>name</label>
    <b-form-input type="text" v-model="name" placeholder="Enter your name"></b-form-input>
    <label>Email</label>
    <b-form-input type="email" v-model="email" placeholder="Enter your email"></b-form-input>
    <label>Password</label>
    <b-form-input type="password" v-model="password" placeholder="Enter your password"></b-form-input>
    <button type="submit" style="background-color:blue; color:white">Register</button>
  </form>
</template>

<script>
export default {
  name: 'Register',
  data () {
    return {
      name: '',
      email: '',
      password: ''
    }
  },
  methods: {
    registerProcess () {
      const payload = {
        name: this.name,
        email: this.email,
        password: this.password
      }
      this.$store.dispatch('registerOn', payload)
    }
  }
}
</script>

<style>
  .register-manual button, label {
    margin-top: 10px;
  }
</style>
