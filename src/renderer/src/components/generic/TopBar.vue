<script setup lang="ts">
const props = defineProps({
  text: String
})
</script>

<template>
  <div class="topbar">{{ props.text }}</div>
</template>

<style lang="css">
@import '../../assets/base.css';

.topbar {
  position: absolute;
  top: 0;
  width: 100%;
  height: 3rem;
  background-color: var(--ev-c-gray-1);
}
</style>
