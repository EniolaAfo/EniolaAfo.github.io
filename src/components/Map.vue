<script setup lang="ts">
import { GoogleMap, Marker } from 'vue3-google-map'
const API_KEY = 'AIzaSyCDb_MADsid6GoRfTNaNqhcQwfk6EiF4XA';
const center = { lat: 40.689247, lng: -74.044502 }
var locations = String();
let headers = new Headers();
headers.append('Access-Control-Allow-Origin', 'http://localhost:5173');
headers.append('Access-Control-Allow-Credentials', 'true');
locations = "39.7391536%2C-104.9847034%7C36.455556%2C-116.866667";
fetch('https://maps.googleapis.com/maps/api/elevation/json?locations='+ locations + '&key=' + API_KEY,{
  headers: headers
})
    .then(response => response.json())
    .then(data => data.value = data);
 '39.7391536%2C-104.9847034%7C36.455556%2C-116.866667'
</script>

 <template>
  <GoogleMap
  api-key='AIzaSyCDb_MADsid6GoRfTNaNqhcQwfk6EiF4XA',
  style="width: 100%; height: 500px"
  :center="center"
  :zoom="15"
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
