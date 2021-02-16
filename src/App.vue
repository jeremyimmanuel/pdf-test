<template>
  <div id="app">
    <doc-viewer
      url="file:///home/jeremy/Desktop/pdf/RSbook_ch3.pdf"
    />
  </div>
</template>

<script>
import DocViewer from './components/DocViewer.vue'

export default {
  name: 'App',
  components: {
    DocViewer
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
  margin-top: 60px;
}
</style>
