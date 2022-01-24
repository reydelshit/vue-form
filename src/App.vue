<template>
<h1>sign up form</h1>
<Signup/>
</template>

<script>
import Signup from './components/SignUpForm.vue'

export default {
  name: 'App',
  components: {
    Signup
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
body{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background: #eee;
}
</style>
