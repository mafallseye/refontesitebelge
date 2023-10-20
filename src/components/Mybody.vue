<template>
  
  <div class="row row-cols-1 row-cols-md-5 g-4 mx-auto p-10 bg-base-100">
  <div class="col">
    <a @click=" SowMission()" style="text-decoration: none;">
    <div class="card h-100">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body cursor-pointer">
        <!-- <h5 class="card-title">Card title</h5> -->
        <p class="card-text  text-center">Entreprises belges intéressées par l'Afrique de  l'Ouest</p>
      </div>
    </div>
    </a>
  </div>
  <div class="col">
    <a @click="ShowInfo()" style="text-decoration: none;">
      <div class="card h-100  ">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body cursor-pointer ">
        <!-- <h5 class="card-title">Card title</h5> -->
        <p class="card-text text-center">Informations pour  les entreprises belges.</p>
      </div>
    </div>
    </a>
    
  </div>
  <div class="col">
    <a href="/film-bruxel-en-wolof.mp4"
             style="text-decoration: none;">
    <div class="card h-100">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body">
        <!-- <h5 class="card-title">Card title</h5> -->
        <p class="card-text text-center">Découvrir le  film Brussels en Wolof</p>
      </div>
    </div>
    </a>
  </div>
  <div class="col">
    <a href="https://credorse.com/news/mission-economique-belge-au-senegal"  rel="noopener noreferrer" style="text-decoration: none;">

      <div class="card h-100">
        <!-- <img src="..." class="card-img-top" alt="..."> -->
        <div class="card-body">
          <!-- <h5 class="card-title">Card title</h5> -->
          <p class="card-text text-center">Mission Economique Belge-interview</p>
        </div>
      </div>
    </a>
  </div>
  <div class="col">
    <a href="https://www.abh-ace.be/fr" style="text-decoration: none;">

      <div class="card h-100">
        <!-- <img src="..." class="card-img-top" alt="..."> -->
        <div class="card-body">
          <!-- <h5 class="card-title">Card title</h5> -->
          <p class="card-text text-center">Agence Belge du Commerce extérieur</p>
        </div>
      </div>
    </a>
  </div>
  <div class="col">
    <a href="https://live.eventtia.com/fr/inscription_forafricc" style="text-decoration: none;">
    <div class="card h-100">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body">
        <!-- <h5 class="card-title">Card title</h5> -->
        <p class="card-text text-center">Forum Africain des Industries Culturelles et créatives</p>
      </div>
    </div>
    </a>
  </div>
  <div class="col">
    <a href="/Finexpo-Brochure-FR-2023-Aide%20non%20liée-2023.pdf" style="text-decoration: none;">
    <div class="card h-100">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body">
        <!-- <h5 class="card-title">Card title</h5> -->
        <p class="card-text text-center">Finexpo-Brochure FR</p>
      </div>
    </div>
    </a>
  </div>
  <div class="col">
    <a href="https://www.enabel.be/fr/" style="text-decoration: none;">

      <div class="card h-100">
        <!-- <img src="..." class="card-img-top" alt="..."> -->
        <div class="card-body">
          <!-- <h5 class="card-title">Card title</h5> -->
          <p class="card-text text-center">ENABEL</p>
        </div>
      </div>
    </a>
  </div>
  <div class="col">
    <div class="card h-100">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body">
        <!-- <h5 class="card-title">Card title</h5> -->
        <p class="card-text text-center">Festival international du film de Bruxelles à Dakar</p>
      </div>
    </div>
  </div>
  <div class="col">
    <a href="https://senegal.diplomatie.belgium.be/fr" style="text-decoration: none;">

        <div class="card h-100">
          <!-- <img src="..." class="card-img-top" alt="..."> -->
          <div class="card-body">
            <!-- <h5 class="card-title">Card title</h5> -->
            <p class="card-text text-center">Ambassade de Belgique au sénégal</p>
          </div>
        </div>
    </a>
  </div>
</div>
<!-- -------------------------------modal---------------------------------------------- -->

<!-- Modal -->
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-lg">
    <div class="modal-content">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="exampleModalLabel">Informations pour  les entreprises belges</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        <div class="row row-cols-1 row-cols-md-5 g-4 mx-auto p-10">
  <div class="col">
    <div class="card h-100">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body">
        <!-- <h5 class="card-title">Card title</h5> -->
        <p class="card-text  text-center">Ouvrir une entreprise au Sénégal</p>
      </div>
    </div>
  </div>
  <div class="col">
    
    <div class="card h-100  "  data-bs-toggle="modal" data-bs-target="#exampleModal">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body ">
        <!-- <h5 class="card-title">Card title</h5> -->
        <p class="card-text text-center">Secteurs porteurs au Sénégal</p>
      </div>
    </div>
  </div>
 
  <div class="col">
    <a href="https://lfgab.com/" style="text-decoration: none;">
    <div class="card h-100 ">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body sen1">
        <!-- <h5 class="card-title">Card title</h5> -->
        <p class="card-text text-center hid1">Green building in africa</p>
      </div>
    </div>
    </a>
  </div>
  <div class="col ">
    <a href="https://www.senegal-emergent.com/" style="text-decoration: none;">
    <div class="card h-100 ">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body sen">
        <!-- <h5 class="card-title">Card title</h5> -->
        <p class="card-text text-center hid ">Plan Sénégal émergent</p>
      </div>
    </div>
    </a>
  </div>
  <div class="col">
    <a href="https://www.sec.gouv.sn/" style="text-decoration: none;">
    <div class="card h-100">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body sen2">
        <!-- <h5 class="card-title">Card title</h5> -->
        <p class="card-text text-center hid2">Gouvernement du Sénégal</p>
      </div>
    </div>
    </a>
  </div>
  <div class="col">
    <a href="/Finexpo-Brochure-FR-2023-Aide%20non%20liée-2023.pdf" style="text-decoration: none;">
    <div class="card h-100">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body">
        <!-- <h5 class="card-title">Card title</h5> -->
        <p class="card-text text-center">Finexpo-Brochure FR </p>
      </div>
    </div>
    </a>
  </div>
  <div class="col">
    <a href="https://entreprendre.sn/senegal/" style="text-decoration: none;">
    <div class="card h-100">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body">
        <!-- <h5 class="card-title">Card title</h5> -->
        <p class="card-text text-center">L'entreprenariat au Sénégal</p>
      </div>
    </div>
    </a>
  </div>
  <div class="col">
    <a href="https://www.businessfrance.fr/guide-des-affaires-senegal-2022" style="text-decoration: none;">
    <div class="card h-100">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body">
        <!-- <h5 class="card-title">Card title</h5> -->
        <p class="card-text text-center">Guide des affaires au Sénégal par Business France</p>
      </div>
    </div>
    </a>
  </div>
  <div class="col">
    <a href="https://senegal.diplomatie.belgium.be/fr" style="text-decoration: none;">

        <div class="card h-100">
          <!-- <img src="..." class="card-img-top" alt="..."> -->
          <div class="card-body">
            <!-- <h5 class="card-title">Card title</h5> -->
            <p class="card-text text-center">Ambassade de Belgique au sénégal</p>
          </div>
        </div>
    </a>
  </div>
</div>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>
</template>
<script>
export default{
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
.sen{
  background-image: url("../assets/senegal-emergent.png");
 background-size: cover;
 visibility: hidden;
}
.sen1{
  background-image: url("../assets/green.png");
 background-size: cover;
 visibility: hidden;
}
.sen2{
  background-image: url("../assets/gouv.png");
 background-size: cover;
 visibility: hidden;
}
.sen:hover{
  visibility: visible;
}
.sen1:hover{
  visibility: visible;
}
.sen2:hover{
  visibility: visible;
}
.hid{
  visibility: visible;
}
.hid1{
  visibility: visible;
}
.hid2{
  visibility: visible;
}
.hid:hover{
  visibility: hidden;
}
.hid:active{
  visibility: hidden;
}
</style>