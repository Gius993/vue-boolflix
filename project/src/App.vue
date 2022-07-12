<template>
  <div id="app">
      <AppHeader />
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
  import AppHeader from './components/AppHeader.vue';
export default {
  name: 'App',
  components: {
    // HelloWorld
    AppHeader
  }
}
</script>

<style lang="scss">
 
@import  "./assets/style/setfix.scss";
</style>
