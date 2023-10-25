<template>
  
  <div class="row row-cols-1 row-cols-md-5 g-4 mx-auto p-10 bg-base-100">
  <div class="col">
    <a @click=" SowMission()" style="text-decoration: none;">
    <div class="card h-100 card1 ">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body cursor-pointer">
        <h5 class="card-title text-center">Mission Economique </h5>
        <p class="card-text  text-center">Entreprises belges intéressées par l'Afrique de  l'Ouest</p>
        <button type="button" class="text-white float-end   mt-14  focus:ring-4 focus:outline-none focus:ring-yellow-300 font-medium rounded-lg text-sm p-2.5 text-center inline-flex items-center  dark:bg-yellow-600 dark:hover:bg-yellow-700 dark:focus:ring-yellow-800">
  <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
  </svg>
  <span class="sr-only">Icon description</span>
</button>
      </div>
    </div>
    </a>
  </div>
  <div class="col">
    <a @click="ShowInfo()" style="text-decoration: none;">
      <div class="card h-100 card2 ">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body cursor-pointer ">
        <h5 class="card-title text-center ">Information.</h5>
        <p class="card-text text-center ">Informations utiles pour  les entreprises belges.</p>
        <button type="button" class="text-white float-end  right-0  mt-20 focus:ring-4 focus:outline-none focus:ring-yellow-300 font-medium rounded-lg text-sm p-2.5 text-center inline-flex items-center  dark:bg-yellow-600 dark:hover:bg-yellow-700 dark:focus:ring-yellow-800">
  <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
  </svg>
  <span class="sr-only">Icon description</span>
</button>
      </div>
    </div>
    </a>
    
  </div>
  <div class="col">
    <a href="/film-bruxel-en-wolof.mp4"
             style="text-decoration: none;">
    <div class="card h-100 card3">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body">
        <h5 class="card-title text-center">Découvrir le  film Brussels en Wolof</h5>
        <p class="card-text text-center "> le  film Brussels est traduit en Wolof</p>
        <button type="button" class="text-white float-end   mt-14  focus:ring-4 focus:outline-none focus:ring-yellow-300 font-medium rounded-lg text-sm p-2.5 text-center inline-flex items-center  dark:bg-yellow-600 dark:hover:bg-yellow-700 dark:focus:ring-yellow-800">
  <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
  </svg>
  <span class="sr-only">Icon description</span>
</button>
      </div>
      
    </div>
    </a>
  </div>
  <div class="col">
    <a href="https://credorse.com/news/mission-economique-belge-au-senegal"  rel="noopener noreferrer" style="text-decoration: none;">

      <div class="card h-100 card4">
        <!-- <img src="..." class="card-img-top" alt="..."> -->
        <div class="card-body">
          <h5 class="card-title text-center">Mission Economique Belge-interview</h5>
          <p class="card-text text-center">
            Une  interview pour la mission économique belge au Sénégal du 21 au 25 mai 2023
          </p>
          <button type="button" class="text-white float-end  mt-2  focus:ring-4 focus:outline-none focus:ring-yellow-300 font-medium rounded-lg text-sm p-2.5 text-center inline-flex items-center  dark:bg-yellow-600 dark:hover:bg-yellow-700 dark:focus:ring-yellow-800">
  <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
  </svg>
  <span class="sr-only">Icon description</span>
</button>
        </div>
      </div>
    </a>
  </div>
  <div class="col">
    <a href="https://www.abh-ace.be/fr" style="text-decoration: none;">

      <div class="card h-100 card5">
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
    <div class="card h-100 card6">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body">
        <h5 class="card-title text-center"> Programme FORAFRICC</h5>
        <p class="card-text text-center">Forum Africain des Industries Culturelles et créatives</p>
        <button type="button" class="text-white float-end   focus:ring-4 focus:outline-none focus:ring-yellow-300 font-medium rounded-lg text-sm p-2.5 text-center inline-flex items-center  dark:bg-yellow-600 dark:hover:bg-yellow-700 dark:focus:ring-yellow-800">
  <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
  </svg>
  <span class="sr-only">Icon description</span>
</button>
      </div>
    </div>
    </a>
  </div>
  <div class="col">
    <a href="/Finexpo-Brochure-FR-2023-Aide%20non%20liée-2023.pdf" style="text-decoration: none;">
    <div class="card h-100 card7">
      <!-- <img src="..." class="card-img-top" alt="..."> -->
      <div class="card-body">
        <h5 class="card-title text-center">Finexpo-Brochure FR</h5>
        <p class="card-text text-center">Finexpo a pour
objectif de soutenir l’exportation de
biens d’équipement belges et de
services afférents.</p>
<button type="button" class="text-white float-end   mt-4 focus:ring-4 focus:outline-none focus:ring-yellow-300 font-medium rounded-lg text-sm p-2.5 text-center inline-flex items-center  dark:bg-yellow-600 dark:hover:bg-yellow-700 dark:focus:ring-yellow-800">
  <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
  </svg>
  <span class="sr-only">Icon description</span>
</button>
      </div>
    </div>
    </a>
  </div>
  <div class="col">
    <a href="https://www.enabel.be/fr/country/senegal/" style="text-decoration: none;">

      <div class="card h-100 card8">
        <!-- <img src="..." class="card-img-top" alt="..."> -->
        <div class="card-body">
          <h5 class="card-title text-center">ENABEL</h5>
          <p class="card-text text-center">Enabel est l’agence de développement du gouvernement fédéral belge</p>
          <button type="button" class="text-white float-end   mt-4  focus:ring-4 focus:outline-none focus:ring-yellow-300 font-medium rounded-lg text-sm p-2.5 text-center inline-flex items-center  dark:bg-yellow-600 dark:hover:bg-yellow-700 dark:focus:ring-yellow-800">
  <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
  </svg>
  <span class="sr-only">Icon description</span>
</button>
        </div>
      </div>
    </a>
  </div>
  <div class="col">
    <a href="https://www.fifb.be/" style="text-decoration: none;">

      <div class="card h-100 card9">
        <!-- <img src="..." class="card-img-top" alt="..."> -->
        <div class="card-body ">
          <h5 class="card-title text-center">Festival international du film de Bruxelles à Dakar</h5>
          <p class="card-text text-center">FIFB - Du 14 au 18 Novembre 2023 </p>
          <button type="button" class="text-white float-end   mt-4  focus:ring-4 focus:outline-none focus:ring-yellow-300 font-medium rounded-lg text-sm p-2.5 text-center inline-flex items-center  dark:bg-yellow-600 dark:hover:bg-yellow-700 dark:focus:ring-yellow-800">
  <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
  </svg>
  <span class="sr-only">Icon description</span>
</button>
        </div>
      </div>
    </a>
  </div>
  <div class="col">
    <a href="https://senegal.diplomatie.belgium.be/fr" style="text-decoration: none;">

        <div class="card h-100 card10">
          <!-- <img src="..." class="card-img-top" alt="..."> -->
          <div class="card-body ">
            <h5 class="card-title text-center">Ambassade de Belgique au sénégal </h5>
            <p class="card-text text-center">Toutes les informations pratiques sur notre Ambassade à Dakar.</p>
            <button type="button" class="text-white float-end   mt-4  focus:ring-4 focus:outline-none focus:ring-yellow-300 font-medium rounded-lg text-sm p-2.5 text-center inline-flex items-center  dark:bg-yellow-600 dark:hover:bg-yellow-700 dark:focus:ring-yellow-800">
  <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
  </svg>
  <span class="sr-only">Icon description</span>
</button>
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
.card{
  border-radius: 0px 20px 0 20px;
  animation: appear 0.5s ease-in-out forwards;

}
.card1{
 background-image: url("../assets/fond1.png");
 background-size: cover;

}
.card2{
 background-image: url("../assets/fond2.png");
 background-size: cover;

}
.card3{
 background-image: url("../assets/fond3.png");
 background-size: cover;

}
.card4{
 background-image: url("../assets/fond4.png");
 background-size: cover;

}
.card5{
 background-image: url("../assets/fond5.png");
 background-size: cover;

}
.card6{
 background-image: url("../assets/fond6.png");
 background-size: cover;

}
.card7{
 background-image: url("../assets/fond7.png");
 background-size: cover;

}
.card8{
 background-image: url("../assets/fond8.png");
 background-size: cover;

}
.card9{
 background-image: url("../assets/Fond9.png");
 background-size: cover;

}
.card10{
 background-image: url("../assets/Fond10.png");
 background-size: cover;

}


</style>