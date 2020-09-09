<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <Star></Star>
    <Star></Star>
    <Pop msg='宝贝复合好不好'>复合吧</Pop>
    <Tab></Tab>
    <DTab></DTab>
</div>
</template>
<script>
import Star from './components/Star/star.vue'
import Pop from './components/PopConfirm/pop.vue'
import Tab from './components/Tab/tab.vue'
import DTab from './components/Tab/dynamic.vue'
export default{
  
  components: {
    // HelloWorld,
    Star,
    Pop,
    Tab,
    DTab
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
