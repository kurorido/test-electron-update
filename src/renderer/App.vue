<template>
  <div id="app">
    <h1>Ver 11</h1>
    <div v-html="lines"></div>
  </div>
</template>

<script>
const { ipcRenderer } = require('electron')

export default {
  name: 'upgrade',
  data () {
    return {
      lines: ''
    }
  },
  mounted () {
    console.log('mounted')
    ipcRenderer.on('message', (event, message) => {
      this.lines += message + '<br/>'
    })
  }
}
</script>

<style>
  /* CSS */
</style>
