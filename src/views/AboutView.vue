<template>
  <div class="about">
    <div class="text-center  spin" v-if="isLoading">
 <div class="spinner-grow" style="width: 3rem; height: 3rem;" role="status">
  <span class="visually-hidden">Loading...</span>
</div>
</div>
    <!-- <HelloWorld /> -->
  <!-- <Image />  -->
  <div v-else>

    <MissionEconomique />
  </div>
  
  </div>
</template>
<script >
import Image from '@/components/Image.vue';
import MissionEconomique from '@/components/MissionEconomique.vue';
// import HelloWorld from "@/components/HelloWorld.vue";
export default {
  name: 'about',
  components: {
    Image,
    MissionEconomique,
    // HelloWorld
},
data(){
  return{
    isLoading:true
  }
},
mounted () {
    setTimeout(() => {
      this.isLoading = false
    }, 1000)
  }
}

</script>
<style scoped>
.spin{

padding-top: 25%;
 font-size :32px;

 
}
</style>
