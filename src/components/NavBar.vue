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
  --bg: #283593;
  --fg: #fafafa;
  --hover-bg: #001064;

  --title-fz: 1.5rem;
}

#navbar {
  padding: 0 1.5rem;
  height: calc(var(--title-fz) + (1.5rem * 2));

  background-color: var(--bg);
  color: var(--fg);

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
  font-size: var(--title-fz);
}

.item-container {
  height: 100%;

  flex-grow: 1;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
}

</style>
