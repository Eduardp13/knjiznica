<template>
  <q-page padding>
    <q-card bordered class="q-pa-md">
      <div class="text-h5 text-center">Naša Lokacija</div>
      <!-- mapa -->
      <div id="map" style="height: 500px; margin-top: 20px"></div>

      <!-- Natrag batun -->
      <q-btn
        label="Natrag"
        color="secondary"
        icon="arrow_back"
        class="full-width q-mt-lg"
        @click="$router.push('/')"
      />
    </q-card>
  </q-page>
</template>

<script>
import { ref, onMounted } from "vue";
import * as L from "leaflet";
import "leaflet/dist/leaflet.css";

export default {
  name: "LokacijaPage",
  setup() {
    const initialMap = ref(null);

    onMounted(() => {
      initialMap.value = L.map("map").setView([45.3312, 14.4322], 13);

      L.tileLayer("https://tile.openstreetmap.org/{z}/{x}/{y}.png", {
        maxZoom: 19,
        attribution:
          '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>',
      }).addTo(initialMap.value);
    });

    return {
      initialMap,
    };
  },
};
</script>

<style scoped>
#map {
  border: 1px solid #ccc;
}
</style>
