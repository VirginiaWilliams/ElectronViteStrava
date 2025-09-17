<script setup lang="ts">
import { ref } from 'vue';
import { Days } from '../../enums';

const total = ref(0);

function updateTotal(): void {
  const languageInputs = document.querySelectorAll<HTMLInputElement>(".day-miles");
  let count = 0

  languageInputs.forEach(el => {
    count += Number(el.value);
  });

  total.value = count;

  return;
}
</script>

<template>
  <div class="running-table">
    <table>
      <tbody>
        <tr>
          <th v-for="d in Days" :key="d">{{ d }}</th>
          <th>Total</th>
        </tr>
        <tr>
          <td v-for="d in Days" :key="d">
            <input type="number" class="day-miles" @input="updateTotal">
          </td>
          <td>{{ total }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style lang="css">
@import '../../assets/base.css';

table,
th,
td {
  border: 1px solid white;
}

th,
td {
  width: 6rem;
  text-align: center;
}

input {
  width: 2rem;
}

/* Chrome, Safari, Edge, Opera */
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

/* Firefox */
input[type=number] {
  -moz-appearance: textfield;
}

</style>
