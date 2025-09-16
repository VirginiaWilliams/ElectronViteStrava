<script setup lang="ts">
import { ref } from 'vue';
import TopBar from './components/generic/TopBar.vue';
import Reading from './components/views/Reading.vue';
import Running from './components/views/Running.vue';
import Home from './components/views/Home.vue';

const currentTab = ref('Home')

let tabs = {
  Reading,
  Running,
  Home
}

function changeView(tab: string): void {
  // if (tab == 'Reading') {
  //   currentTab.value = 'Reading'
  // } else if (tab == 'Running') {
  //   currentTab.value = 'Running'
  // } else {
  //   currentTab.value = 'Home'
  // }
  currentTab.value = tab;
}
</script>

<template>
  <TopBar @tab-selected="changeView" />
  <component :is="tabs[currentTab]" class="tab"></component>
</template>
