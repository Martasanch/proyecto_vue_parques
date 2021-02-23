<template>
<div class="prueba">
  <h3>¿Quieres saberlo todo sobre nuestros parques?</h3>
	<select class="form-control form-control-lg" v-model="parque" @change="verSeleccionado" >
	<option value="">Selecciona un parque de Madrid</option>
    <option v-for="(parque,i) in parques" :key="i" :value="parque['@id']">{{parque['title']}}</option>

</select>
	<div class="informacion" v-if="informacion.datos">
		<h4 class="d-flex justify-content-center text-align-center">Información del parque de {{informacion.datos.title}}:</h4>
			<ul>
			<li><span>Descripción:</span> {{informacion.datos.organization['organization-desc']}}:</li>
			<li><span>Servicios:</span>  {{informacion.datos.organization['services']}}:</li>
			<li><span>Horario:</span>  {{informacion.datos.organization['schedule']}}</li>
			<li><span>Más información:</span> <a :href="informacion.datos.relation">{{informacion.datos.relation}}</a></li>
			<li><div id="mapa">
				<Map :lat="latitud" :long="longitud" :dir="direccion"/>	
			</div>
			</li>
			</ul>

	</div>
	

 </div>  

</template>

<script>
import Map from '@/components/Map'
import {ref, reactive} from 'vue'
export default {
    components: {
    Map,
 	},
  
	name: 'Parques',
    setup(){
	
    let parques=reactive([])
	let parque=ref("")
	let informacion=reactive([])
	let latitud=ref("")
	let longitud=ref("")
	let direccion=ref("")



	fetch("https://datos.madrid.es/egob/catalogo/200761-0-parques-jardines.json")
	.then(res=>res.json())
	.then(datos=>{
		//console.log(datos['@graph'][0]['title'])
		console.log(datos)
		datos['@graph'].forEach(element => {parques.push(element)
		})
	})

	 function verSeleccionado(){
		console.log(parque.value)
		//alert("El dato del parque es "+parque.value)
			
			fetch(parque.value)
			.then(res=>res.json())
			.then(info=>{
				console.log(info)
				//console.log(info['@graph'][0]) 
				informacion.datos=info['@graph'][0]
				latitud.value=informacion.datos.location['latitude']
				longitud.value=informacion.datos.location['longitude']
				direccion.value=informacion.datos.address['street-address']
			
	 })

	 }
	 

    return{parques, parque, verSeleccionado, informacion, latitud, longitud, direccion
    }
}
   
}
   
</script>

<style lang="scss" scoped>


.prueba{
	option{
			height: 50px;
	}
	h3{
		padding-top: 70px;
		margin-bottom: 50px;
		font-weight: bold;
	}
	.form-control{
		width: 350px;
		margin:auto;
	}
	
  .informacion{
	margin-left: auto;
    margin-right:auto;
	margin-top: 20px;
	padding:20px;
	box-sizing: content-box;
	width: 80%;
	border: 1px solid black;
	display: block;
	text-align: left;
	background-color: rgba(255, 255, 255, 0.782);
		h4{
			
			font-weight: bold;
		}
		li{
			border:1px solid whitesmoke;
			padding: 10px;
			list-style:none;
			span{
				font-size: large;
				font-weight: bold;

			}
		}
	}
}
          
</style>