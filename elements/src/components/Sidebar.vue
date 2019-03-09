<template>
  <div class="sidebar">
    <div class="sidebar-item" 
      v-for="item in items" 
      :key="item"
      @click="itemClicked(item)">
        {{ item }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'Sidebar',
  data() {
    return {
      items: [
        'Intro',
        'Fincher',
        'Wright',
        'Tarantino'
      ]
    }
  },
  methods: {
    itemClicked(item) {
      this.$emit('item-clicked', item)
    },
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .sidebar {
    writing-mode: vertical-rl;
    text-orientation: mixed;
    display: flex;
    justify-content: center; 
  }
  .sidebar {
    display: flex; 
    justify-content: space-evenly;
    &-item {
      cursor: pointer;
      padding: 2em 1em;
      border:  1px solid #2B2B31;
      text-transform: uppercase;
      font-size: 16px;
      &:hover {
        border:  1px solid #FFFFFF
      }
    }
  }
</style>
