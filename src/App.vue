<template>
  <hello-world/>
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

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  margin: 0;
  padding: 0;
    /* box-sizing: border-box; */
  background-image: url('@/assets/meow.jpg');
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  
}
</style>
