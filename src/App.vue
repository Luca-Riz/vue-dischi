<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Deserunt, aut. Natus quas aperiam maxime consequuntur tempora inventore incidunt itaque, doloremque perspiciatis adipisci, temporibus, corrupti quasi similique minima at voluptas ipsam.</p>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style lang="scss">
@import '@/style/general.scss';


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
