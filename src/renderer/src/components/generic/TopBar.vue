<script setup lang="ts">
// TODO: Change this to an enum
let tabs = ['Home', 'Reading', 'Running']

const emit = defineEmits(['tab-selected'])

function onClick(tab: string): void {
  emit('tab-selected', tab);
}
</script>

<template>
  <div class="topbar">
    <div v-for="tab in tabs" :key="tab">
      <div class="tab" @click="onClick(tab)">
        {{ tab }}
      </div>
    </div>
  </div>
</template>

<style lang="css">
@import '../../assets/base.css';

.topbar {
  position: absolute;
  top: 0;
  width: 100%;
  height: 3rem;
  background-color: var(--ev-c-gray-3);
  display: flex;
  line-height: 3rem;
}

.tab {
  padding: 0 1rem 0 1rem;
}

.tab:hover {
  background-color: var(--ev-c-gray-1);
}
</style>
