<template>
  <item-list/>
</template>

<script>
import ItemList from './components/ItemList'

export default {
  name: 'App',
  components: {
    ItemList
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  display: flex;
  justify-content: center;
}
</style>
