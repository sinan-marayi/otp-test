<template>
  <OTP />
</template>

<script>
import OTP from './components/OTP.vue'

export default {
  name: 'App',
  components: {
    OTP
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
