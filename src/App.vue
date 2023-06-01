<template>
  <Binding /><hr/>
  <ConditionalRendering /><hr/>
  <ListRendering /><hr/>
  <EventHandling />
</template>

<script>
import Binding from './components/1_Binding.vue'
import ConditionalRendering from './components/2_ConditionalRendering.vue'
import ListRendering from './components/3_ListRendering.vue';
import EventHandling from './components/4_EventHandling.vue';
export default {
  name: 'App',
  components: {
    Binding,
    ConditionalRendering,
    ListRendering,
    EventHandling
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
