<template>
  <div class="tabs">
    <div class="tab-buttons">
      <TabButton
          v-for="(tab, index) in tabs"
          :key="index"
          :name="tab.$props.name"
          @click.native="() => handleTabButtonClick(tab.$props.name)"
      />
      <slot></slot>
    </div>
  </div>
</template>

<script>
import TabButton from './TabButton.vue'
import TabComponent from './TabComponent.vue'

export default {
  name: 'TabsComponent',
  components: {
    TabComponent,
    TabButton
  },
  data() {
    return {
      tabs: []
    }
  },
  mounted () {
    this.tabs = [ ...this.$children ]
  },
  methods: {
    handleTabButtonClick(tabName) {
      this.tabs.forEach((tab, index) => {
        tab.activeInternal = tab.$props.name === tabName
      })
    }
  }
}
</script>

<style scoped>

</style>