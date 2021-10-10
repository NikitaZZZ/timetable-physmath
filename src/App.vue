<template>
  <timetable />
</template>

<script>
import timetable from './components/timetable.vue'
import 'bootstrap/dist/css/bootstrap.min.css';

export default {
  name: 'App',
  components: {
    timetable
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
}
</style>
