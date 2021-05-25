<template>
  <div v-if="activeInternal">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'TabComponent',
  props: {
    active: {
      type: Boolean,
      default: false
    },
    name: {
      type: String,
      required: true,
    }
  },
  data() {
    return {
      activeInternal: this.active
    }
  }
}
</script>

<style scoped>
  div {
    padding: 10px;
    background-color: aliceblue;
  }
</style>