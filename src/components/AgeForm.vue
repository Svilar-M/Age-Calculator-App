<template>
  <form @submit.prevent="submitForm" class="mb-4">
    <div class="mb-2">
      <label for="day" class="block text-sm font-medium text-gray-700">Day</label>
      <input
        type="number"
        id="day"
        v-model="day"
        class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
        required
      />
    </div>
    <div class="mb-2">
      <label for="month" class="block text-sm font-medium text-gray-700">Month</label>
      <input
        type="number"
        id="month"
        v-model="month"
        class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
        required
      />
    </div>
    <div class="mb-2">
      <label for="year" class="block text-sm font-medium text-gray-700">Year</label>
      <input
        type="number"
        id="year"
        v-model="year"
        class="mt-1 block w-full px-3 py-2 border border-gray-300 rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
        required
      />
    </div>
    <button
      type="submit"
      class="mt-3 w-full inline-flex justify-center py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
    >
      Calculate Age
    </button>
  </form>
</template>

<script setup>
import { ref, defineEmits } from 'vue';

const day = ref('');
const month = ref('');
const year = ref('');

const emit = defineEmits(['calculate-age']);

const submitForm = () => {
  const birthDate = { day: Number(day.value), month: Number(month.value), year: Number(year.value) };
  emit('calculate-age', birthDate);
};
</script>