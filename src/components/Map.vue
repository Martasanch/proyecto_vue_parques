<template>
  <div class="map">
    <div class="botones d-flex justify-content-center">
     <button class="btn btn-primary" @click="popUpinfo">Ver dirección</button>
   </div>
   <div id="mapid"></div>
   
  </div>
</template>

<script>
// la librería leaftet la instalamos de npm: vue2-leaflet, de ella importamos L

import L from "leaflet"
import {ref, reactive, onMounted} from "vue"
export default {
name: 'Map',
props:{
	  lat: Number,
	  long: Number,
    dir: String
  },
setup(props){
  //console.log(props)
  let latitud=props.lat
  let longitud=props.long
  let direccion=props.dir
  let mymap
  let marker






function popUpinfo(){
    var popup = L.popup()
        .setLatLng([latitud, longitud])
        .setContent(direccion)
        .openOn(mymap);
}

onMounted(()=>{
    mymap = L.map('mapid').setView([40.43540109145338, -3.6932684399079823], 11) //pongo las coordenadas de mi zona (las copio de google map)
    L.tileLayer('https://api.mapbox.com/styles/v1/{id}/tiles/{z}/{x}/{y}?access_token={accessToken}', {
        attribution: 'Map data &copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
        maxZoom: 18,
        id: 'mapbox/streets-v11',
        tileSize: 512,
        zoomOffset: -1,
        accessToken: 'pk.eyJ1IjoibWFydGFzYW5jaCIsImEiOiJja2xhcWNiNTUxYzB5MnBucG54bzhpNjkzIn0.l_YU6JtaWVlx58pLL7Po4w' //me registro para obtener el token
    }).addTo(mymap)
    marker=L.marker([latitud, longitud]).addTo(mymap)

})

  return{ popUpinfo, latitud, longitud, direccion}
}
} 
</script>





<style lang="scss" scoped>
#mapid { 
  margin-top:10px;
  margin-left:auto;
  margin-right:auto;
 
  height:300px;
  width: 500px;
 }
</style>