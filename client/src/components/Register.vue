<template>
  <div>
    <h1>Register Component</h1>
    <input type="email" name="email" v-model="email" placeholder="email"/>
    <br/>
    <input type="password" name="password" v-model="password" placeholder="password"/>
    <br/>
    <button @click="register">Register</button>
  </div>
</template>

<script>
import Authentication from '@/services/Authentication'
export default {
  data () {
    return {
      email: 'abc',
      password: 'xyz'
    }
  },
  methods: {
    async register () {
      console.log('Register button clicked', this.email, this.password)
      const response = await Authentication.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data)
    }
  }
}
</script>

<style>

</style>
