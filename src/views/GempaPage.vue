<template>
  <main-layout title="Gempa">
    <ion-card>
      <div class="map" ref="mapRef"></div>
    </ion-card>
    <ion-card color="light">
      <ion-card-header>
        <ion-card-title>
          <p style="font-size: large;">Gempa Bumi (Yogyakarta)</p>
        </ion-card-title>
        <ion-card-subtitle>27 Juli 2023 - 20.03 WIB</ion-card-subtitle>
      </ion-card-header>

      <ion-card-content>
        <div class="earthquake-detail">
          <span class="magnitude"><strong>Magnitude:</strong> 6.7 SR</span>
          <span class="depth"><strong>Depth:</strong> 10 km</span>
          <span class="location"><strong>Location:</strong> -7.79°S, 110.37°E </span>
          <span class="tsunami-warning">Tidak berpotensi tsunami.</span>
        </div>
      </ion-card-content>

    </ion-card>

  </main-layout>
</template>
<script setup>
import { IonCard, IonCardContent, IonCardHeader, IonCardSubtitle, IonCardTitle } from '@ionic/vue';
import MainLayout from '../components/layout/MainLayout.vue';
import { ref, onMounted } from 'vue';
import { Geolocation } from '@capacitor/geolocation';

const mapRef = ref(null);
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

const initializeGoogleMaps = () => {
  if (window.google?.maps) {
    initMap();
    return;
  }

  const key = "AIzaSyA1TnLmVoq_tj_pSfVPbmzpXvdWrpFa0Qs";  // Please replace with your Google Maps API key.
  const googleMapScript = document.createElement("SCRIPT");
  googleMapScript.src = `https://maps.googleapis.com/maps/api/js?key=${key}&callback=initMap`;
  googleMapScript.defer = true;
  googleMapScript.async = true;
  document.head.appendChild(googleMapScript);
};

const initMap = () => {
  const mapInstance = new google.maps.Map(mapRef.value, {
    zoom: 8,
    center: { lat:-7.798270297936324, lng: 110.3732486838921 },
    disableDefaultUI: true,
  });
  const marker = new google.maps.Marker({  // Added 'new' keyword here
    position:  { lat:-7.798270297936324, lng: 110.3732486838921 },
    map: mapInstance,
    title: "Current Location"
  });
};

onMounted(() => {
  printCurrentPosition();
  initializeGoogleMaps();
});

// Avoid overriding any existing functions.
if (!window.initMap) {
  window.initMap = initMap;
}
</script>

<style scoped>
.earthquake-detail {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  gap: 8px 12px;
}

.earthquake-detail span {
  display: block;
  padding: 4px 0;
}

.magnitude,
.depth,
.location {
  border-bottom: 1px solid rgba(0, 0, 0, 0.1);
  /* subtle line for separation */
}

.location{
  grid-column: 1 / 3;

}

.tsunami-warning {
  grid-column: 1 / 3;
  /* spans the full width */
  font-weight: bold;
  /* emphasize the tsunami warning */
  color: #d32f2f;
  /* give it a reddish color for warning, adjust if needed */
}

.map {
  width: 100%;
  height: 300px;
}</style>
