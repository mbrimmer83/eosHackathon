<template>
  <div class="tabs-container">
    <v-tabs
        v-model="active"
        color="#f5f5f5"
        slider-color="#f5f5f5"
        grow
      >
        <v-tab
          v-for="(item, key) in items"
          :key="key"
        >
          {{ item.name }}

        </v-tab>
        <v-tab-item
          v-for="(item, key) in items"
          :key="key"
        >
          <v-card flat>
            <v-card-text>
              <component v-bind:is="item.component"></component>
            </v-card-text>
          </v-card>
        </v-tab-item>
    </v-tabs>
  </div>
</template>

<script>

import UserTabDummy from './UserTabDummy'
import UserAccountTab from './UserAccountTab'
import UserHistoryTab from './UserHistoryTab'

export default {
  components: {
    // eslint-disable-next-line
    UserTabDummy,
    // eslint-disable-next-line
    UserAccountTab,
    // eslint-disable-next-line
    UserHistoryTab
  },
  data: function() {
    return {
    items: [
      { name: 'History', component: 'UserHistoryTab' },
      { name: 'Account', component: 'UserAccountTab' },
      { name: 'Score', component: 'UserTabDummy' },
      { name: 'Soi', component: 'UserTabDummy' },
      { name: 'Family', component: 'UserTabDummy' }]
    }
  }
}
</script>

<style>
  .tabs-container {
    width: 46%;
    margin: 10px 10px 10px 10px;
  }
  .v-tabs__item--active {
    border: 1px solid #D3D3D3;
    border-radius: 5px;
  }
</style>
