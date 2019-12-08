<template>
  <div id="app">
    <to-do></to-do>
  </div>
</template>

<script>
import ToDo from './components/ToDo.vue'
export default {
  name: 'app',
  components: {
    ToDo
  }
}
</script>

<style>
    body {
      font-family: 'tahoma'
    }
    .btn {
        border-radius: .25rem;
        float: right;
        border-style: solid;
    }
</style>
