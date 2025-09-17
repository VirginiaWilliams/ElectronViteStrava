<script setup lang="ts">
import RunningTable from './RunningTable.vue';
</script>

<template>
  <div class="mileage-planner">
    <RunningTable :days="7" />
  </div>
</template>

<style lang="css">
@import '../../assets/base.css';

.mileage-planner {
  width: 100%;
  background-color: var(--ev-c-gray-3);
  display: flex;
  flex-direction: row;;
}

.single-day {
  padding: 8px;
}
</style>
