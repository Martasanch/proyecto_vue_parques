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
			<li><span>Dirección:</span>  {{informacion.datos.address['street-address']}}</li>
			<li><span>Coordenadas:</span><br>  {{informacion.datos.location['latitude']}}<br>
			{{informacion.datos.location['longitude']}}</li>
			</ul>

	</div>


</div>   

</template>

<script>

import {ref, reactive} from 'vue'
export default {
    name: 'Parques',
    setup(){
	
    let parques=reactive([])
	let parque=ref("")
	let informacion=reactive([])
	


	fetch("https://datos.madrid.es/egob/catalogo/200761-0-parques-jardines.json")
	.then(res=>res.json())
	.then(datos=>{
		console.log(datos['@graph'])
		datos['@graph'].forEach(element => {parques.push(element)
		})
	})

	 function verSeleccionado(){
		console.log(parque.value)
		/* alert("El dato del parque es "+parque.value) */
			
			fetch(parque.value)
			.then(res=>res.json())
			.then(info=>{
				console.log(info['@graph'][0]) 
				informacion.datos=info['@graph'][0]
		
	 })

	 }
	 

    return{parques, parque, verSeleccionado, informacion
    }
}
   
}
   
</script>

<style lang="scss" scoped>

.prueba{
	height: 800px;
 	background-image:url("../assets/logo7.jpg");
	background-size: cover;
	background-repeat:repeat;

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
          
</style>