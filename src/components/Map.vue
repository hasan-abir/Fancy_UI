<template>
  <div>
    <div id="map"></div>
  </div>
</template>

<script>
import L from "leaflet"
import "leaflet/dist/leaflet.css"

export default {
  name: "map",
  mounted() {
    this.map = L.map("map").setView([23.8103, 90.4125], 18)

    const marker = L.marker([23.8103, 90.4125]).addTo(this.map)

    const popup = `<p>Bangladesh</p>`

    marker
      .bindPopup(popup, {
        maxWidth: "auto"
      })
      .openPopup()

    L.tileLayer("https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png", {
      attribution:
        'Map data &copy; <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
      maxZoom: 18,
      minZoom: 18,
      id: "mapbox.streets"
      // accessToken: 'pk.eyJ1IjoiYWJpcm1lYWRvd3MiLCJhIjoiY2p5cHVqdzY1MGUzcDNodWd1aXA1MnVwdyJ9.2oPWD8a4wnf6vLSiJvnFLA'
    }).addTo(this.map)
  }
}
</script>

<style>
#map {
  min-height: 800px;
  width: 100%;
  z-index: 1;
}
</style>
