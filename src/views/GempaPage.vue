<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Gempa</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true" class="ion-padding">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Gempa</ion-title>
        </ion-toolbar>
      </ion-header>


      <!-- Displaying the Geolocation values -->
      <div v-if="coordinates" class="centered">
        <p>Latitude: {{ coordinates.latitude }}</p>
        <p>Longitude: {{ coordinates.longitude }}</p>
      </div>

    </ion-content>
  </ion-page>
</template>

<script setup>
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
import { ref } from 'vue';
import { Geolocation } from '@capacitor/geolocation';

// Reactive data for coordinates
const coordinates = ref(null);

const printCurrentPosition = async () => {
  try {
    const position = await Geolocation.getCurrentPosition();
    coordinates.value = {
      latitude: position.coords.latitude,
      longitude: position.coords.longitude
    };
  } catch (error) {
    console.error("Failed to get geolocation:", error);
  }
};

printCurrentPosition();
</script>

<style scoped>
.centered {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%; /* Set this to the height of the parent container */
}
</style>
