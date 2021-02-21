<template>
  <div class="parques">
   <!-- <img alt="logo4" src="../assets/logo4.jpg" height="300">  -->
  <!--  <img alt="logo4" src="../assets/logo7.jpg" height="300"> 
    -->
   
    <p>
     <Parques/>
    </p>
  </div>
</template>

<script>
import Parques from '@/components/Parques'
import {ref, reactive, onMounted} from "vue"
export default {
  components: {
    Parques
  },
setup(){


  return{}
}
} 
</script>





<style lang="scss" scoped>
/* .parques{
  background-image:url("../assets/logo7.jpg");
    background-size: cover;
  background-repeat:no-repeat;
} */
</style>