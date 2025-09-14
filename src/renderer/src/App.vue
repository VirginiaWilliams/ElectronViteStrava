<script setup lang="ts">
import { computed, ref } from 'vue';
import TopBar from './components/generic/TopBar.vue';
import ReadingView from './components/reading/ReadingView.vue';
import RunningView from './components/running/RunningView.vue';

const routes = {
  '/reading': ReadingView,
  '/running': RunningView
}

const currentPath = ref(window.location.hash);

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
})

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/']
})
</script>

<template>
  <TopBar></TopBar>
  <div class="title">Welcome!</div>
  <a href="#/reading">Reading</a> |
  <a href="#/running">Running</a>
  <component :is="currentView" />
</template>
