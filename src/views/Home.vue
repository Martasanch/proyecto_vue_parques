<template>
<!--   <div class="img">
    <img alt="logo2" src="../assets/logo2b.jpg" height="400"> 
  </div> -->
<!--   <div class="cabecera">
    <div class="texto">
    
    <h2>Una guía de los parques y jardines del municipio de Madrid</h2>
    </div>
  </div> -->
  <div id="carouselExampleCaptions" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-indicators">
    <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
    <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="1" aria-label="Slide 2"></button>
    <button type="button" data-bs-target="#carouselExampleCaptions" data-bs-slide-to="2" aria-label="Slide 3"></button>
  </div>
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="../assets/logo2b.jpg" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
        <h1>Bienvenid@ a Madrid en Verde</h1>
        <h2>Una buscador de parques y jardines del municipio de Madrid</h2>
      </div>
    </div>
    <div class="carousel-item">
      <img src="../assets/logo2b.jpg" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
        <h1>¿Eres un artista callejero?</h1>
        <h2>¡Queremos saber cúando y dónde tocas!</h2>
      </div>
    </div>
    <div class="carousel-item">
      <img src="../assets/logo2b.jpg" class="d-block w-100" alt="...">
      <div class="carousel-caption d-none d-md-block">
        <h1>¿Practicas deporte al aire libre?</h1>
        <h2>Seguro que hay gente deseando unirse a tus entrenamientos.</h2>
      </div>
    </div>
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleCaptions"  data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleCaptions"  data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>

<div class="texto">
  <h5>Contribuye a darle vida a nuestros parques, consolidándolos como espacios de recreo, culturales, sociales y deportivos. 
  </h5>


<div class="row tarjetas d-flex justify-content-center">
    <div class="card card1" style="width: 18rem;">
  <img src="../assets/logo6.jpg" class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Actividades</h5>
    <p class="card-text">Nuestros parques son espacios recreativos, pero tambien son ideales para relacionarnos, o incluso para practicar deporte en grupo.<br>¿Quieres informarnos de alguna de tus actividades?</p>
  </div>
 
  <div class="card-body">
    <a href="#" class="card-link">Card link</a>
    <a href="#" class="card-link">Another link</a>
  </div>
</div>
    <div class="card card2" style="width: 18rem;">
  <img src="../assets/logo13.jpg" class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Desconexión</h5>
    <p class="card-text">¿Estás estresado? quizá necesitas desconectar de la jungla de asfalto, respirar aire limpio, o disfrutar de una puesta de sol. Descubre los mejores lugares, y sube tus fotos para que otros usuarios puedan verlas. </p>
  </div>
 
  <div class="card-body">
    <a href="#" class="card-link">Card link</a>
    <a href="#" class="card-link">Another link</a>
  </div>
</div>
    <div class="card card3" style="width: 18rem;">
  <img src="../assets/logo11.jpg" class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Street music</h5>
    <p class="card-text">Entérate en tiempo real de las actuaciones de nuestros artistas callejeros, y disfruta de la música al aire libre.</p>
  </div>
 
  <div class="card-body">
    <a href="#" class="card-link">Card link</a>
    <a href="#" class="card-link">Another link</a>
  </div>
</div>
</div>
</div>

</template>

<script>
// @ is an alias to /src
//import from 

export default {
  name: 'Home',
  components: {
 
  }
}
</script>
<style lang="scss" scoped>
/* .img{
  height: 50px;
  border: solid 4px whitesmoke;
  background-size: cover
} */
/* .cabecera{
  padding-top: 80px;
  color:whitesmoke;
  height: 400px;
  background-image: url(../assets/logo2.jpg);
  background-size: cover;
  background-repeat:no-repeat;
  


  }  */

.texto{
  
  width: 70%;
  margin-right: auto;
  margin-left: auto;
  margin-top: 30px;
  padding:20px;
  border: solid 3px honeydew;
  background-color: rgba(172, 255, 47, 0.524);
  h4{text-align: center;}
}
  h1{
    font-size: 60px;
    margin-bottom: 50px;
    font-weight: bolder;
   
   
   } 
   h2{
     font-weight: bold;
  

}
.card{
  margin: 20px 50px;
  
}
</style>
