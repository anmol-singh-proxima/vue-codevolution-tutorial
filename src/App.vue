<template>
  <Binding /><hr/>
  <ConditionalRendering /><hr/>
  <ListRendering />
</template>

<script>
import Binding from './components/1_Binding.vue'
import ConditionalRendering from './components/2_ConditionalRendering.vue'
import ListRendering from './components/3_ListRendering.vue';
export default {
  name: 'App',
  components: {
    Binding,
    ConditionalRendering,
    ListRendering,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
}
h1 {
  text-decoration: underline;
}
</style>
