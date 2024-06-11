<template>
  <div v-if="age" class="mt-4 p-4 bg-green-100 rounded-md">
    <p>You are {{ age.years }} years, {{ age.months }} months, and {{ age.days }} days old.</p>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

defineProps({
  age: {
    type: Object,
    default: null,
  },
});
</script>