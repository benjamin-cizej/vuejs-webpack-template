<template>
  <button type="button">{{ name }}</button>
</template>

<script>
export default {
  name: 'TabButton',
  props: {
    name: {
      type: String,
      required: true,
    }
  }
}
</script>

<style scoped>

</style>