<template>
  <div id="app">
    <button @click="play()">Play</button>
    <tama ref="tama" :x="100" :y="500" :scale-x="0.5" :scale-y="0.5" :rotate="0"></tama>
  </div>
</template>

<script>
import Tama from "./components/Tama"

export default {
  name: 'app',
  components: {
    Tama
  },
  methods: {
    async play() {
      const tama = this.$refs.tama
      await tama.jump(100, 1500)
      await tama.walk(100, 1200)
      await tama.walk(60, 600)
      await tama.walk(40, 400)
      await tama.jump(200, 2500)
    }
  }
}
</script>

<style lang="scss">
html, body {
  margin: 0;
  padding: 0;
}
body {
  position: relative;
  height: 100%;
  background: url('/img/grid.svg') repeat;
}
#app {
  margin: 0;
}
</style>
