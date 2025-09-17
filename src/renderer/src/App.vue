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
  currentTab.value = tab;
}
</script>

<template>
  <TopBar @tab-selected="changeView" />
  <component :is="tabs[currentTab]"></component>
</template>
