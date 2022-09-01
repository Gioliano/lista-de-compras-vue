<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png">
    <shopping-list msg="Vue3 App"/>
</div>
  
</template>

<script>
import shoppingList from './components/shoppingList.vue'


export default {
  name: 'App',
  components: { shoppingList },
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
