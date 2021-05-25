<template>
  <div>
    <TabsComponent>
      <TabComponent name="First tab">
        <p>First tab content</p>
      </TabComponent>
      <TabComponent name="Second Tab">
        <h2>Second tab content</h2>
      </TabComponent>
      <TabComponent name="Third tab" :active="true">
        <p>Third tab content</p>
      </TabComponent>
      <TabComponent
          name="Fourth tab"
          :ajax-source="true"
          :fetch-source="fetchAjaxContent"
      ></TabComponent>
    </TabsComponent>
  </div>
</template>

<script>

import TabsComponent from './components/TabsComponent'
import TabComponent from './components/TabComponent'
export default {
  name: 'App',
  components: {
    TabComponent,
    TabsComponent,
  },
  methods: {
    fetchAjaxContent() {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          resolve({
            data: '<h2>Ajax content</h2>'
          })
        }, 3000)
      })
    }
  }
}
</script>

<style>

</style>