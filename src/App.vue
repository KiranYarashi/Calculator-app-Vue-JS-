<template>
  <div id="app">
    <h1>Calculator App</h1>
    <Calculator />
  </div>
</template>

<script>
import Calculator from './components/CalCulator.vue';

export default {
  name: 'App',
  components: {
    Calculator,
  },
};
</script>

<style>
#app {
  text-align: center;
  margin-top: 20px;
}
</style>
