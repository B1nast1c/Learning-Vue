<template>
  <div id="app">
    <router-view />
  </div>
</template>

<script>
/* eslint-disable */
import Login from "./components/Login"

export default {
  name: 'App',
  components: {
    Login
  }
}
</script>

<style>
#app{
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
