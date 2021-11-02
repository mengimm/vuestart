<template>  
<LoginForm />  
  <Timer />
  
</template>

<script>

import LoginForm from './components/loginform.vue'
import Timer from './components/timer.vue'

export default {
  name: 'App',
  components: {
    LoginForm,
    Timer,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
