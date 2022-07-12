<template>
  <div id="app">
      <AppHeader />
      <AppMain />
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
  import AppHeader from './components/AppHeader.vue';
  import AppMain from './components/AppMain.vue'
export default {
  name: 'App',
  components: {
    // HelloWorld
    AppHeader,
    AppMain
  }
}
</script>

<style lang="scss">
 
@import  "./assets/style/setfix.scss";
</style>
