<script setup>
import { ref } from 'vue';
import CardCuaca from '../molecul/CardCuaca.vue';

// Sample data for demonstration purposes
const weatherData = ref([
  { location: 'Kemayoran', temperature: '27°C', condition: 'Cloudy' },
  { location: 'Cempaka Putih', temperature: '28°C', condition: 'Sunny' },
]);
</script>

<template lang="">
  <div>
    <CardCuaca 
      v-for="data in weatherData" 
      :key="data.location" 
      :data="data"
    ></CardCuaca>
  </div>
</template>

<style lang=""></style>
