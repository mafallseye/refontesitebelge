<template>
  <div class="about">
    <!-- <HelloWorld /> -->
  <!-- <Image />  -->
  
    <MissionEconomique />
  
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
}

</script>
