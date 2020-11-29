<template>
  <NavBar :title="title" :options="options" />
</template>

<script>
import NavBar from './components/NavBar.vue'

export default {
  name: 'App',
  components: {
    NavBar
  },
  data() {
    return {
      title: "My Web Page",
      options: [
        { type: "item", tag: "Who Am I", url: "#" },
        { type: "item", tag: "Where Am I", url: "#" },
        { type: "item", tag: "Which Am I", url: "#" },
        { type: "dropdown", tag: "Projects", url: "#", children: [
          { type: "item", tag: "Anaconda", url: "#" },
          { type: "item", tag: "Thingy", url: "#" },
        ] },
      ]
    }
  },
}
</script>

<style>
#app {
}
</style>
