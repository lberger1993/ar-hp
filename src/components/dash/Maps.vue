<script>
const VueGoogleMap = require('vue-google-maps')
VueGoogleMap.load({key: 'AIzaSyDbvxvRkkpfLq5DHdIuCCDlZecfwUu83Ig'})

module.exports = {
  name: 'Maps',
  data () {
    return {
      center: {lat: 10.0, lng: 10.0},
      markers: [{
        position: {lat: 10.0, lng: 10.0}
      }, {
        position: {lat: 11.0, lng: 11.0}
      }]
    }
  }
}
</script>
<template>
  <map
    :center="center"
    :zoom="7"
  >
    <marker 
      v-for="m in markers"
      :position.sync="m.position"
      :clickable="true"
      :draggable="true"
      @g-click="center=m.position"
    ></marker>
  </map>
</template>