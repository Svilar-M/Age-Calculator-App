<template>
  <div class="container mx-auto p-4">
    <h1 class="text-2xl font-bold mb-4">Age Calculator</h1>
    <AgeForm @calculate-age="calculateAge" />
    <AgeResult :age="age" />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import AgeForm from './components/AgeForm.vue';
import AgeResult from './components/AgeResult.vue';

const age = ref(null);

const calculateAge = (birthDate) => {
  const today = new Date();
  const birth = new Date(birthDate.year, birthDate.month - 1, birthDate.day);
  let years = today.getFullYear() - birth.getFullYear();
  let months = today.getMonth() - birth.getMonth();
  let days = today.getDate() - birth.getDate();

  if (days < 0) {
    months -= 1;
    days += new Date(today.getFullYear(), today.getMonth(), 0).getDate();
  }

  if (months < 0) {
    years -= 1;
    months += 12;
  }

  age.value = { years, months, days };
};
</script>

<style scoped>
body {
  font-family: Arial, sans-serif;
}
</style>