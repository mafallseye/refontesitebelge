<template>
  <div class=" HelloWorld">
    <nav class="navbar navbar-expand-lg bg-body-tertiary">
      <div class="container-fluid">
        <!-- <a class="navbar-brand" href="#">Navbar</a> -->
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <a class="nav-link " aria-current="page" href="/">Accueil
              </a>
            </li>
            <li class="nav-item">
              <a class="nav-link"  @click=" SowMission()">Entreprises belges & secteurs</a>
            </li>
            <li class="nav-item">
              <a class="nav-link"  @click=" ShowListEntrepriseSenegal()">Entreprise du sénégal</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">
                Organisateurs
              </a>
            </li>
            <li class="nav-item">
              <a class="nav-link"  @click=" ShowInfo()">
                Informations pour les entreprises belges
              </a>
            </li>
            <li class="nav-item">
              <a class="nav-link"  @click="ShowRevue()">
                Revue de presse
              </a>
            </li>
            
           
          </ul>
      
        </div>
      </div>
    </nav>
  </div>


</template>

<script>
export default {
  name: 'HelloWorld',
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
.nav-item :active{
background-color: white;
}
</style>


