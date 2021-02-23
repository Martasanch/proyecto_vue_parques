<template>
  <div class="parques">

    <div>
     <Parques/>
    </div>
   
  </div>

</template>

<script>
import Parques from '@/components/Parques'

import {ref, reactive, onMounted} from "vue"
export default {
  components: {
    Parques,
  
    
  },
setup(){


  return{}
}
} 
</script>





<style lang="scss" scoped>
.parques{

	height: 1300px ;
 	background-image:url("../assets/img1.jpg");
	background-size: cover;
	background-repeat:repeat;



}

</style>