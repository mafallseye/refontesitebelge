<template>
  <div class="home">

    <!-- <HelloWorld /> -->
    <Image />
    <div>

      <Search />
    </div>
    <Mybody />
    <Organisateur />
    <MyFooter />

 
  


  </div>
</template>


<script>
import MyFooter from "@/components/MyFooter.vue";
import Organisateur from "@/components/Organisateur.vue";
import Mybody from "@/components/Mybody.vue";
import Search from "@/components/Search.vue";
import Image from '@/components/Image.vue';

// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    Image,
    Search,
   Mybody,
   Organisateur,
    MyFooter
},
  data(){
   return{
    secteurs:[
      {
       nom:"Agriculture / Agroalimentaire / Aliments / Boissons",
       tof:""
      },
      {
       nom:"Services / Consultance",
       tof:""
      },
      {
       nom:"Médical / Pharmaceutique / Chimie",
       tof:""
      },
      {
       nom: "Médical / Pharmaceutique / Chimie",
       tof:""
      },
      {
       nom: "Énergie / Eau / Environnement / Technologies propres",
       tof:""
      },
      
      {
       nom: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
       tof:""
      },
      {
       nom: "Construction services / Infrastructures / Ingénieries",
       tof:""
      },
      {
       nom: "Fédérations / Chambres de Commerce / Associations / Presse",
       tof:""
      },
      {
       nom: "Transports et Logistique",
       tof:""
      },
      {
       nom: "Luxe / Textile / Mode / Bien-être",
       tof:""
      },
      {
       nom: "Éducation",
       tof:""
      },
      {
       nom: "Services financiers",
       tof:""
      },
      {
       nom: "ICT et électronique",
       tof:""
      },
      
      {
       nom: "Industries culturelles et créatives/loisirs/tourisme",
       tof:""
      },
      
    ]
   }
  }

}

</script>
<style scoped>

</style>

