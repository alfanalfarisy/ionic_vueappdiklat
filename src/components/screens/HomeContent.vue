<script setup>
import { ref, onMounted } from 'vue';
import CardGempa from '../molecul/CardGempa.vue'
import CardCuacaFind from '../molecul/CardCuacaFind.vue'
import Loader from '../molecul/Loader.vue'

const data = ref(null);
const isLoading = ref(true);

async function fetchData(url) {
  try {
    const response = await fetch(url);
    const json = await response.json();
   
    data.value = json;
  } catch (json) {
    console.error("Error fetching data:", error);
  } finally {
    isLoading.value = false;
  }
}

onMounted(() => {
  fetchData('https://training06.devbmkg.my.id/gempa-terbaru');
});

</script>

<template>
  <CardCuacaFind></CardCuacaFind>
  <div v-if="isLoading"><Loader></Loader></div>
  <CardGempa v-else :data="data"></CardGempa>
</template>

<style lang=""></style>
