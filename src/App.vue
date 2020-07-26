<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
	<CirclePoccess></CirclePoccess>
	 <img alt="Vue logo" src="./assets/logo.png">
	 <ButtonI></ButtonI>
	 <SeveviceItem style="width: 100px;height: 100px;"></SeveviceItem>
  </div>
</template>

<script>
	import "./assets/public.css"
import HelloWorld from './components/HelloWorld.vue'
import  CirclePoccess from './components/CirclePoccessItem.vue'
import  SeveviceItem from './components/SeveviceItem.vue'
import ButtonI from "./components/ButtonI.vue"
export default {
  name: 'app',
  components: {
    HelloWorld,
	CirclePoccess,
	SeveviceItem,
	ButtonI
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: lightgrey;
  height: 100vh;
}
</style>
