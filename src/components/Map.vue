<script setup lang="ts">
import { GoogleMap, Marker } from 'vue3-google-map'

const center = { lat: 40.689247, lng: -74.044502 }
</script>

<template>
  <GoogleMap
    api-key="AIzaSyCDb_MADsid6GoRfTNaNqhcQwfk6EiF4XA"
    style="width: 100%; height: 500px"
    :center="center"
    :zoom="10"
  >
    <Marker :options="{ position: center }" />
  </GoogleMap>
</template>
<style>
#map {
  height: 100%;
}
html,
body {
  height: 100%;
  margin: 0;
  padding: 0;
}
</style>
