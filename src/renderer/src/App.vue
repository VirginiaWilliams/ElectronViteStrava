<script setup lang="ts">
import Button from './components/Button.vue'
import TopBar from './components/TopBar.vue'

function handleFileUpload(event): void {
  const file = event.target.files[0];
  if (file) {
    const reader = new FileReader();
    reader.onload = (e) => {
      const csvContent = e.target!.result;
      processCsvData(csvContent);
    };
    reader.readAsText(file); // Read the file as text
  }
}

function processCsvData(csvContent): void {
  // This is where you'll parse the CSV content
  console.log('csvContent: ', csvContent);
}
</script>

<template>
  <TopBar></TopBar>
  <div class="title">Upload your CSV to see your stats!</div>
  <div class="sub-title">(Must be exported from storygraph)</div>
  <div class="actions">
    <Button :text="'hello'" />
  </div>
  <input type="file" accept=".csv" @change="handleFileUpload" />
</template>

<style lang="css">
.title {
  font-size: 28px;
  color: var(--ev-c-text-1);
  font-weight: 700;
  line-height: 32px;
  text-align: center;
  margin: 0 10px;
  padding: 16px 0;
}

.sub-title {
  font-size: 16px;
  line-height: 24px;
  color: var(--ev-c-text-2);
  font-weight: 600;
}
</style>
