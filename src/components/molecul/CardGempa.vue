<template lang="">
  <section v-if="data">
      <div class="gempa p-3 mb-4">
          <div class="card p-2 rounded shadow">
              <div class="text-center fw-bold">Gempabumi Dirasakan</div>
              <div class="mb-2 text-center">{{ data.date }}</div>
              <div id="map"></div>
              <div class="d-flex flex-row justify-content-around p-2">
                  <div>
                      <img
                          src="https://warning.bmkg.go.id/img/magnitude.png"
                          alt="Magnitudo"
                          width="26"
                          height="26"
                      /> 
                      <strong>{{ data.magnitude }}</strong><br/>
                      <span> Magnitudo</span>
                  </div>
                  <div>
                      <img
                          src="https://warning.bmkg.go.id/img/kedalaman.png"
                          alt="Kedalaman"
                          width="26"
                          height="26"
                      />
                      <strong>{{ data.depth }}</strong> <br/><span> Kedalaman</span>
                  </div>
                  <div>
                      <img
                          src="https://warning.bmkg.go.id/img/koordinat.png"
                          alt="Koordinat"
                          width="26"
                          height="26"
                      />
                      <strong>{{ data.latitude }} <br />{{ data.longitude }}</strong>
                  </div>
              </div>
          </div>
      </div>
  </section>
</template>

<script setup>

import { defineProps, onMounted } from 'vue';
import L from 'leaflet';
import 'leaflet/dist/leaflet.css';

const { data } = defineProps(['data']);

onMounted(() => {
  const coordinates = data.coordinates.split(',').map(coord => parseFloat(coord.trim())).reverse()
  const map = L.map("map").setView(coordinates, 6);
  L.tileLayer(
    "https://server.arcgisonline.com/ArcGIS/rest/services/World_Street_Map/MapServer/tile/{z}/{y}/{x}",
    {
      maxZoom: 19,
      attribution: "&copy; BMKG",
    }
  ).addTo(map);

  L.marker(coordinates).addTo(map);
});

</script>

<style lang="">

</style>
