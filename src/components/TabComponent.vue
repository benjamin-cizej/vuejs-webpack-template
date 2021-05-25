<template>
  <div>
    <template v-if="ajaxSource">
      <div v-if="activeInternal" v-html="content">
      </div>
    </template>
    <template v-else>
      <div v-if="activeInternal">
        <slot></slot>
      </div>
    </template>
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
    },
    ajaxSource: {
      type: Boolean,
      default: false
    },
    fetchSource: {
      type: Function,
      default: () => {}
    }
  },
  data() {
    return {
      activeInternal: this.active,
      content: ''
    }
  },
  mounted () {
    console.log(this.$slots)
  },
  watch: {
    activeInternal(value) {
      if (!this.ajaxSource) {
        return
      }

      if (value && !this.content) {
        this.fetchSource()
          .then((response) => {
            this.content = response.data
          })
          .catch(() => {

          })
      }
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