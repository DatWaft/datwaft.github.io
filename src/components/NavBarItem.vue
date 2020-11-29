<template>
  <div :class="item.type">
    <template v-if="item.type == 'item'">
      <div class="tag" @click="go()">
        {{ item.tag }}
      </div>
    </template>
    <template v-else-if="item.type == 'dropdown'">
      <div class="tag clickable" @click="toggle()">
        {{ item.tag }}
        <font-awesome-icon icon="arrow-down" v-if="dropped" />
        <font-awesome-icon icon="arrow-up" v-else />
      </div>
      <div class="item-container" v-if="dropped">
        <NavBarItem v-for="(child, i) in item.children" :item="child" :key="i" />
      </div>
    </template>
  </div>
</template>

<script>
export default {
  name: 'NavBarItem',
  props: {
    item: Object,
  },
  data() {
    return {
      dropped: false
    }
  },
  methods: {
    toggle() {
      this.dropped = !this.dropped
    },
    go() {
      window.location = this.item.url
    },
  }
}
</script>

<style scoped>

.item,
.dropdown {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;

  height: 100%;

  background-color: var(--bg);
  color: var(--fg);

  display: flex;
  justify-content: space-around;
  align-items: center;
}

.tag {
  flex-grow: 1;
  
  width: 100%;
  height: 100%;
  padding: 1rem 1rem;

  display: flex;
  justify-content: space-around;
  align-items: center;

  cursor: pointer;
}

.item:hover,
.dropdown:hover {
  background-color: var(--hover-bg);
}

.dropdown {
  position: relative;
}

.dropdown > .item-container {
  position: absolute;
  top: 100%;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
}

.clickable {
  cursor: pointer;
}

</style>
