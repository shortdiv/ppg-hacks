<template>
  <div id="map"></div>
</template>

<script>
import mapboxgl from 'mapbox-gl'
const MapboxClient = require('mapbox')

export default {
  name: 'Home',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      map: null
    }
  },
  getLngLat () {
    var mbClient = new MapboxClient('pk.eyJ1Ijoic2hvcnRkaXYiLCJhIjoiY2l3OGc5YmE5MDJzZjJ5bWhkdDZieGdzcSJ9.1z-swTWtcCHYI_RawDJCEw')
    return mbClient.geocodeForward('Singapore, Singapore', function (err, result) {
      if (err) { console.log(err) }
      console.log(result)
    })
  },
  mounted () {
    this.$options.getLngLat().then((res) => {
      console.log(res.entity.features[0].center)
    })
    mapboxgl.accessToken = 'pk.eyJ1Ijoic2hvcnRkaXYiLCJhIjoiY2l3OGc5YmE5MDJzZjJ5bWhkdDZieGdzcSJ9.1z-swTWtcCHYI_RawDJCEw'
    const map = new mapboxgl.Map({
      container: 'map',
      style: 'mapbox://styles/mapbox/light-v9',
      center: [103.81983600000001, 1.352083],
      zoom: 11
    })
    this.$data.map = map
    // hack for now //
    document.querySelector('.mapboxgl-canvas').style.position = 'relative'
  }
}
</script>
<style scoped>
body {
  margin: 0; 
  padding: 0;
}
#map { 
  top: 0; 
  bottom: 0; 
  width: 100%; 
  max-width: none;
  position:absolute;
}
.mapboxgl-canvas {
  position:relative !important;
}
</style>
