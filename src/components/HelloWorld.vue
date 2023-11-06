<template>
  <div class=" HelloWorld">
    <nav class="navbar navbar-expand-lg bg-base-100">
      <div class="container-fluid">
        <!-- <a class="navbar-brand" href="#">Navbar</a> -->
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav m-auto mb-2 mb-lg-0 uppercase ">
            <li class="nav-item text-base font-medium text-gray-900 cursor-pointer">
              <router-link to="/" class="nav-link ">Accueil
              </router-link>
            </li>
            <li class="nav-item text-base font-medium text-gray-900  cursor-pointer">
              <router-link  to="/mission-economigque-belge-au-senegal" class="nav-link"  @click=" SowMission()">Entreprises belges & secteurs</router-link>
            </li>
            <li class="nav-item text-base font-medium text-gray-900 cursor-pointer">
              
              <router-link to="/information" class="nav-link"  @click=" ShowInfo()">
                Informations pour les entreprises belges
              </router-link>
            </li>
            <li class="nav-item text-base font-medium text-gray-900 cursor-pointer">
              <router-link to="/entreprise-au-senegal" class="nav-link"  @click=" ShowListEntrepriseSenegal()">Entreprise du sénégal</router-link>
            </li>
            <!-- <li class="nav-item  cursor-pointer">
              <router-link class="nav-link bg-white" to="#organisateurs">
                Organisateurs
              </router-link>
            </li> -->
           
            <li class="nav-item text-base font-medium text-gray-900  cursor-pointer">
              <router-link to="/revue-presse" class="nav-link"  @click="ShowRevue()">
                Revue de presse
              </router-link>
            </li>
            
           
          </ul>
      
        </div>
      </div>
    </nav>
  </div>


</template>

<script>
import Organisateur from "./Organisateur.vue";
export default {
  name: 'HelloWorld',
  components:{
Organisateur
  },
  data(){
    return{}

  },
methods:{
  SowMission(){
    this.$router.push("/mission-economigque-belge-au-senegal")
  },
  ShowListEntrepriseSenegal(){
    this.$router.push("/entreprise-au-senegal")
  },
  ShowInfo(){
    this.$router.push("/information")
  },
  ShowRevue(){
    this.$router.push("/revue-presse") 
  }
}
}

</script>
<style scoped>
a{
  visibility: visible;
}
a.router-link-active{
  border-bottom:4px solid #bbb;
}

</style>


