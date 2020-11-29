<template>
  <NavBar :title="title" :options="options" />
  <div style="display: flex; justify-content: center; align-items: center; flex-grow: 1;">
    <div style="
      font-size: 5rem;
      user-select: none;
      opacity: 25%;
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;">
      This site is WIP
    </div>
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
        { type: "item", tag: "Who Am I", url: "#who" },
        { type: "item", tag: "Where Am I", url: "#where" },
        { type: "item", tag: "Which Am I", url: "#which" },
        { type: "dropdown", tag: "Projects", children: [
          { type: "item", tag: "Anaconda", url: "#anaconda" },
          { type: "dropdown", tag: "Cute", children: [
            { type: "item", tag: "Panda", url: "#panda" },
            { type: "item", tag: "Rabbit", url: "#rabbit" },
          ] },
          { type: "item", tag: "Thingy", url: "#thingy" },
        ] },
      ]
    }
  },
}
</script>

<style>
#app {
  flex-grow: 1;

  display: flex;
  flex-direction: column;
}

:root,
body {
  height: 100%;
}

body {
  margin: 0;

  display: flex;
}
</style>
