<template>
  <section id="location" class="location reveal">
    <h2>Место проведения</h2>
    <p>Ресторан "Актаныш"</p>
    <p>с. Актаныш, ул Ленина</p>
    <div id="map" class="map"></div>
    <h3>Dress Code: Элегантный стиль</h3>
  </section>
</template>

<script setup>
import { onMounted } from 'vue'
import L from 'leaflet'
import 'leaflet/dist/leaflet.css'
import iconUrl from 'leaflet/dist/images/marker-icon.png'
import iconRetinaUrl from 'leaflet/dist/images/marker-icon-2x.png'
import shadowUrl from 'leaflet/dist/images/marker-shadow.png'

onMounted(() => {
  const coords = [55.7331, 53.2039]
  const map = L.map('map').setView(coords, 15)
  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '© OpenStreetMap contributors',
  }).addTo(map)
  const icon = L.icon({ iconUrl, iconRetinaUrl, shadowUrl, iconSize: [25, 41], iconAnchor: [12, 41] })
  L.marker(coords, { icon }).addTo(map)
})
</script>

<style scoped>
.location {
  text-align: center;
  padding: 4rem 2rem 2rem;
}

.map {
  height: 300px;
  width: 100%;
  margin-top: 1rem;
}

@media (max-width: 600px) {
  .location {
    padding: 2rem 1rem;
  }
}
</style>
