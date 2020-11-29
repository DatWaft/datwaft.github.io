<template>
  <div id="navbar">
    <div class="title">
      {{ title }}
    </div>
    <div class="item-container">
      <NavBarItem v-for="(o, i) in options" :item="o" :key="i"/>
    </div>
  </div>
</template>

<script>

import NavBarItem from './NavBarItem.vue'

export default {
  name: 'NavBar',
  components: {
    NavBarItem
  },
  props: {
    title: String,
    options: Array,
  },
}
</script>

<style scoped>

#navbar {
  padding: 0 2rem;

  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

#navbar * {
  user-select: none;
}

.title {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  font-weight: bold;
  font-size: 2rem;
}

.item-container {
  flex-grow: 1;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
}

</style>
