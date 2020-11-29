<template>
  <div :class="item.type">
    <template v-if="item.type == 'item'">
      <div class="tag">
        <a :href="item.url">{{ item.tag }}</a>
      </div>
    </template>
    <template v-else-if="item.type == 'dropdown'">
      <div class="tag clickable" @click="toggle()">
          {{ item.tag }}
          <font-awesome-icon :icon="icon" />
      </div>
      <div class="item-container">
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
  computed: {
    icon() {
      return this.dropped ? "arrow-down" : "arrow-up"
    }
  },
  methods: {
    toggle() {
      this.dropped = !this.dropped
    }
  }
}
</script>

<style scoped>

.item,
.dropdown {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

.clickable {
  cursor: pointer;
}

a {
  text-decoration: none;
  color: inherit;
}

</style>
