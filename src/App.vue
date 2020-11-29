<template>
  <NavBar :title="title" :options="options" />
  <div style="display: flex; justify-content: center; align-items: center; height: 100%;">
    <div style="font-size: 5rem;">This site is WIP</div>
  </div>
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
        { type: "dropdown", tag: "Projects", children: [
          { type: "item", tag: "Anaconda", url: "#" },
          { type: "dropdown", tag: "Cute", children: [
            { type: "item", tag: "Panda", url: "#" },
            { type: "item", tag: "Rabbit", url: "#" },
          ] },
          { type: "item", tag: "Thingy", url: "#" },
        ] },
      ]
    }
  },
}
</script>

<style>
#app {
  height: 100%;
}

:root,
body {
  height: 100%;
}

body {
  margin: 0;
}
</style>
