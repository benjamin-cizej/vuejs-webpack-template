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
}
</script>

<style>

</style>