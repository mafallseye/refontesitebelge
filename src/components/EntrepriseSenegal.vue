<template>
<HelloWorld />
<ImageSenegal />

    <nav class="flex  px-10 py-6" aria-label="Breadcrumb">
      <ol class="inline-flex items-center space-x-1 md:space-x-3">
        <li class="inline-flex items-center">
          <a href="/"
            class="inline-flex items-center text-sm font-medium text-gray-700 hover:text-gray-900 dark:text-gray-400 dark:hover:text-white">
            <svg class="mr-2 w-4 h-4" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
              <path
                d="M10.707 2.293a1 1 0 00-1.414 0l-7 7a1 1 0 001.414 1.414L4 10.414V17a1 1 0 001 1h2a1 1 0 001-1v-2a1 1 0 011-1h2a1 1 0 011 1v2a1 1 0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 0 001.414-1.414l-7-7z">
              </path>
            </svg>
          </a>
        </li>
        <li>
          <div class="flex items-center">
            <svg class="w-6 h-6 text-gray-400" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd"
                d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z"
                clip-rule="evenodd"></path>
            </svg>
            <a href="#entreprise"
              class="ml-1 text-sm font-medium text-gray-700 hover:text-gray-900 md:ml-2 dark:text-gray-400 dark:hover:text-white">Entreprises
              & secteurs au sénégal</a>
          </div>
        </li>
        <li v-if="searchSector != ''">
          <div class="flex items-center">
            <svg class="w-6 h-6 text-gray-400" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd"
                d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z"
                clip-rule="evenodd"></path>
            </svg>
            <a href="#entreprise"
              class="ml-1 text-sm font-medium text-gray-700 hover:text-gray-900 md:ml-2 dark:text-gray-400 dark:hover:text-white">
              <span   class="bg-gray-100 text-gray-800 text-xs font-medium mr-2 px-2.5 py-0.5 rounded-full dark:bg-gray-900 dark:text-gray-300">{{ searchSector }}</span>
            </a>
          </div>
        </li>

      </ol>
    </nav>



    <section class="bg-white dark:bg-gray-900">
    <div class="py-8 px-4 mx-auto max-w-screen-xl sm:py-16 lg:px-6">
      <div class="max-w-screen-xl p-10 text-left mb-8 lg:mb-16">
        <label id="entreprise"
          class="m-1 inline-flex carde items-center px-5 py-1 text-sm font-normal text-center text-gray-900 active:text-gray-900 bg-gray-100 rounded-full active:bg-gray-600 focus:ring-4 focus:outline-none active:ring-gray-300 dark:bg-gray-600 dark:hover:bg-gray-700 dark:focus:ring-gray-800">
          <input type="radio" v-model="searchSector" value="" />
          Sélectionner tout
          <!-- <span
              class="inline-flex justify-center items-center ml-2 w-4 h-4 text-xs font-semibold text-gay-900 bg-gray-400 rounded-full">
              171
            </span> -->
        </label>
        <label v-for="sect in this.secteur" :key="sect.nom" :class="{ checked: sect.checked }"
          class="m-1 inline-flex carde items-center px-5 py-1 text-sm font-normal text-center text-gray-900 active:text-gray-900 bg-gray-100 rounded-full">
          <input type="radio" v-model="searchSector" :value="sect.nom" />
          {{ sect.nom }}
          <span
            class="inline-flex justify-center items-center ml-2 w-4 h-4 text-xs font-semibold text-gay-900 bg-gray-400 rounded-full">
            {{ sect.nombre }}
          </span>
        </label>
      </div>
      <!-- <div id="inscription" class="w-full p-6 bg-white text-right dark:bg-gray-800 dark:border-gray-700">
          <a @click="showInscription()">
           
            <button
              class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-white bg-red-600 rounded-r-full rounded-t-full hover:bg-gray-800 focus:ring-4 focus:outline-none focus:ring-gray-300 dark:bg-gray-600 dark:hover:bg-gray-700 dark:focus:ring-gray-800">
              Inscrivez-vous
              <svg aria-hidden="true" class="w-4 h-4 ml-2 -mr-1" fill="currentColor" viewBox="0 0 20 20"
                xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd"
                  d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z"
                  clip-rule="evenodd"></path>
              </svg>
            </button>
          </a>
       
        </div> -->
       >>> <span  v-if="searchSector != ''"  class="bg-blue-100 text-blue-800 text-xs font-medium mr-2 px-2.5 py-0.5 rounded-full dark:bg-red-900 dark:text-blue-300">{{ searchSector }}</span>

      <div class="relative overflow-x-auto shadow-md sm:rounded-lg">

        <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400">
          <thead class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
            
            <tr>
              <th colspan="4" scope="col" class="px-10 py-6">

                <form>
                  <label for="default-search"
                    class="mb-2 text-sm font-medium text-gray-900 sr-only dark:text-white">Search</label>
                  <div class="relative">
                    <div class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none">
                      <svg aria-hidden="true" class="w-5 h-5 text-gray-500 dark:text-gray-400" fill="none"
                        stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                          d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path>
                      </svg>
                    </div>
                    <input type="search" id="default-search" v-model="filter"
                      class="block w-full p-4 pl-10 text-sm text-gray-900 border border-gray-300 rounded-lg bg-white focus:ring-blue-500 focus:border-blue-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                      placeholder="cherche le nom d'une entreprise" required autocomplete="off">

                  </div>
                </form>

              </th>
            </tr>
            <tr>
              <th scope="col" class="px-6 py-3">
                <span class="sr-only">Edit</span>
              </th>
              <th scope="col" class="px-6 py-3" @click="sort('nom')">
                <div class="flex items-center">
                  Entreprises
                  <a href="#"><svg xmlns="http://www.w3.org/2000/svg" class="w-3 h-3 ml-1" aria-hidden="true"
                      fill="currentColor" viewBox="0 0 320 512">
                      <path
                        d="M27.66 224h264.7c24.6 0 36.89-29.78 19.54-47.12l-132.3-136.8c-5.406-5.406-12.47-8.107-19.53-8.107c-7.055 0-14.09 2.701-19.45 8.107L8.119 176.9C-9.229 194.2 3.055 224 27.66 224zM292.3 288H27.66c-24.6 0-36.89 29.77-19.54 47.12l132.5 136.8C145.9 477.3 152.1 480 160 480c7.053 0 14.12-2.703 19.53-8.109l132.3-136.8C329.2 317.8 316.9 288 292.3 288z" />
                    </svg></a>
                </div>
              </th>
              <th scope="col" class="px-6 py-3" @click="sort('profil')">
                <div class="flex items-center">
                  Descriptif de l'activité
                  <a href="#"><svg xmlns="http://www.w3.org/2000/svg" class="w-3 h-3 ml-1" aria-hidden="true"
                      fill="currentColor" viewBox="0 0 320 512">
                      <path
                        d="M27.66 224h264.7c24.6 0 36.89-29.78 19.54-47.12l-132.3-136.8c-5.406-5.406-12.47-8.107-19.53-8.107c-7.055 0-14.09 2.701-19.45 8.107L8.119 176.9C-9.229 194.2 3.055 224 27.66 224zM292.3 288H27.66c-24.6 0-36.89 29.77-19.54 47.12l132.5 136.8C145.9 477.3 152.1 480 160 480c7.053 0 14.12-2.703 19.53-8.109l132.3-136.8C329.2 317.8 316.9 288 292.3 288z" />
                    </svg></a>
                </div>
              </th>
              <th scope="col" class="px-6 py-3">
                <div class="flex items-center">
                  Visitez le site web
                  <a href="#"><svg xmlns="http://www.w3.org/2000/svg" class="w-3 h-3 ml-1" aria-hidden="true"
                      fill="currentColor" viewBox="0 0 320 512">
                      <path
                        d="M27.66 224h264.7c24.6 0 36.89-29.78 19.54-47.12l-132.3-136.8c-5.406-5.406-12.47-8.107-19.53-8.107c-7.055 0-14.09 2.701-19.45 8.107L8.119 176.9C-9.229 194.2 3.055 224 27.66 224zM292.3 288H27.66c-24.6 0-36.89 29.77-19.54 47.12l132.5 136.8C145.9 477.3 152.1 480 160 480c7.053 0 14.12-2.703 19.53-8.109l132.3-136.8C329.2 317.8 316.9 288 292.3 288z" />
                    </svg></a>
                </div>
              </th>


            </tr>
          </thead>
          <tbody>

            <tr v-for="entreprise in setSearchSector" :key="entreprise.nom"
              class="bg-white border-b dark:bg-gray-800 dark:border-gray-700">
              <th scope="row" class="px-6 py-4 font-medium text-gray-900 whitespace-nowrap dark:text-white">
                <span v-if="entreprise.image != ''">
                  <img class="w-60 h-10 " :src="require(`@/img/${entreprise.image}.png`)" alt="Default avatar">


                </span>
              </th>
              <th scope="row" class="px-6 py-4 font-medium text-gray-900 whitespace-nowrap dark:text-white">
                {{ entreprise.nom }}
              </th>
              <td class="px-6 py-4">
                {{ entreprise.profil }}
              </td>
              <td class="px-6 py-4">
                <span>
                  <a :href="`${entreprise.site}`">
                    <svg class="w-5 h-5 ml-2 text-blue-600" fill="currentColor" viewBox="0 0 20 20"
                      xmlns="http://www.w3.org/2000/svg">
                      <path
                        d="M11 3a1 1 0 100 2h2.586l-6.293 6.293a1 1 0 101.414 1.414L15 6.414V9a1 1 0 102 0V4a1 1 0 00-1-1h-5z">
                      </path>
                      <path d="M5 5a2 2 0 00-2 2v8a2 2 0 002 2h8a2 2 0 002-2v-3a1 1 0 10-2 0v3H5V7h3a1 1 0 000-2H5z">
                      </path>
                    </svg>
                  </a>

                </span>
              </td>


            </tr>







          </tbody>
        </table>


        <VueTailwindPagination :current="currentPage" :total="total" :per-page="pageSize"
          @page-changed="currentPage = $event" text-before-input="Aller à la page" text-after-input="Aller" />

      </div>


    </div>
  </section>
 
<Organisateur/>
<MyFooter />
</template>
<script>



import VueTailwindPagination from "@ocrv/vue-tailwind-pagination"
import '@ocrv/vue-tailwind-pagination/styles';
import HelloWorld from "./HelloWorld.vue";
import ImageSenegal from "./ImageSenegal.vue";
import MyFooter from "./MyFooter.vue";
import Organisateur from "./Organisateur.vue";
export default {
  components: {
  
    VueTailwindPagination,
 
   Organisateur,
    HelloWorld,
    ImageSenegal,
    MyFooter
},
  data() {
    return {
      pageSize: 10,
      total: 200,
      currentPage: 1,
      currentSort: "nom",
      currentSortDir: "asc",
      partLenth: 10,
      showing: 1,
      searchQuery: "",
      searchSector: "",
      isVisible: false,
      showMenu: false,
      filter: '',
      secteur: [
        {
          nom: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nombre: 52,
        },
        {
          nom: "ICT et électronique",
          nombre: 38,
        },
        {
          nom: "Transport et logistique",
          nombre: 14,
        },
        {
          nom: "Services / Consultance",
          nombre: 31,
        },
        {
          nom: "Construction services / Infrastructure / Ingénieurie",
          nombre: 48,
        },
        {
          nom: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nombre: 31,
        },
        // {
        //   nom: "Metallurgie",
        //   nombre: 3,
        // },
        {
          nom: "Médical / Pharmaceutique / Chimie",
          nombre: 14,
        },
        // {
        //   nom: "Électricité",
        //   nombre: 1,
        // },
        {
          nom: "Éducation",
          nombre: 18,
        },
        {
          nom: "Luxe / Textile / Mode / Bien-être",
          nombre: 17,
        },
        {
          nom: "Services financiers",
          nombre: 39,
        },
        {
          nom: "Énergie / Eau / Environement / Technologies propres",
          nombre: 41,
        },
        {
          nom: "Industries culturelles et créatives / loisirs / Tourisme",
          nombre: 0,
        },
        {
          nom: "Fédération et chambre de commerce",
          nombre: 12,
        },
        {
          nom: "Machines et Materiels",
          nombre: 12,
        },

      ],
      listentreprise: [
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Afitex",
          profil:
            "Spécialiste santé et alimentation animale.",
          image: "",
          site: "https://afitex.net/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "AFAO WAWA",
          profil:
            "Autonomisation des femmes, renforcement des capacités à travers diverses formations notamment la transformation des produits agroalimentaires.",
          image: "",
          site: "https://www.food-security.net/actor/association-des-femmes-de-lafrique-de-louest-afao0wawa/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "agCelerant",
          profil:
            "Plateforme de développement commercial déployée par MANOBI AFRICA pour restructurer le secteur agricole africain en chaînes de valeur organisées, transparentes, efficaces et inclusives.",
          image: "agcelerant_v2_300dpi-2048x469",
          site: "https://www.agcelerant.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Agence Nationale d’Insertion et de Développement Agricole (ANIDA)",
          profil:
            "Promouvoir le développement d’une agriculture moderne, diversifiée, basée sur la maîtrise de l’eau et pourvoyeuse d’emplois rémunérateurs et durables pour les jeunes.",
          image: "anida",
          site: "https://sn.linkedin.com/in/anida-senegal-33783b246",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Agrisen",
          profil:
            "Production de fruits et légumes.",
          image: "AgriSenegal-logo-fond-vert-V2-e1639263082822",
          site: "https://agrisenegal.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Agro Expedition Sénégal/Filiale de Silas Export Holding BV",
          profil:
            "Production locale, traitement et stockage des oignons et pommes de terre, import et export.",
          image: "logo-agro-senegal-2",
          site: "https://agro-senegal.com/",
        },

        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Agroline",
          profil:
            "Entreprise agro-alimentaire spécialisée dans la tomate.",
          image: "Logo-Agroline",
          site: "https://agroline.sn/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "AMO INDUSTRIE",
          profil:
            "Raffinerie de sel spécialisée dans la production et la commercialisation du sel fin sec iodé.",
          image: "amo",
          site: "https://amoindustries.sn/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Buursine International",
          profil:
            "Production et exportation de mangues, d'ananas, de noix de cajou et d'arachides Bio.",
          image: "buursine",
          site: "https://www.buursine.de",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Cereal Investments Company (CIC)",
          profil:
            "Importateur et Distributeur de produits agricoles tels que le riz, le maïs, le sucre, l’huile végétale, le lait en poudre, le soja, le tourteau de soja ainsi que le blé, présent en Côte d’Ivoire, au Sénégal, au Cap Vert, au Ghana, au Niger, en Mozambique et en Guinée-Bissau.",
          image: "cicglobal",
          site: "https://www.cic-global.com",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Compagnie sucrière sénégalaise (CSS)",
          profil:
            "Entreprise Agro-industrielle réalisant l'ensemble des opérations de transformation de la canne en sucre raffiné.",
          image: "css",
          site: "https://www.css.sn/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Delphinus Sénégal",
          profil:
            "Import et export de poissons, premier chargeur de Air France depuis le Sénégal.",
          image: "2da0d8_63083aa83a8941aa895e574bf605aebd_mv2",
          site: "https://www.delphinus-sn.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Domaine Agricole de NEMA (DAN)",
          profil:
            "Production et exportation de fruits et légumes frais de qualité.",
          image: "dan",
          site: "https://www.facebook.com/profile.php?id=100063482380958&mibextid=ZbWKwL",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "EUROGERM",
          profil:
            "Spécialisés dans la conception, la fabrication et la commercialisation d’ingrédients et de solutions créatives pour la filière blé-farine- pain-pâtisserie, experts en croustillant, moelleux, goût et texture, nous partageons avec nos clients la même passion du pain, de la viennoiserie et de la pâtisserie.",
          image: "logo-eg-header-blanc",
          site: "https://www.eurogerm-senegal.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Faraal Djigueeni Sénégal",
          profil:
            "Transformation et commercialisation des produits locaux du sénégal notamment la marque LALA.",
          image: "LOGO_3D_200x@2x",
          site: "https://lalaorganics.store/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Fisapac Afrique",
          profil:
            "Cafés, cappucinos, thés et chocolats.",
          image: "fisapac-afrique-logo-1615367992",
          site: "https://fisapac.sn/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Grands Moulins de Dakar",
          profil:
            "Industrie meunière.",
          image: "gmd-contour",
          site: "https://www.gmd.sn/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "IBRIZ",
          profil:
            "Société de technologie solaire axée sur l’utilisation productive de l’énergie solaire dans l’agriculture.",
          image: "Attachment_1621121723",
          site: "https://www.ibriz.co",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "International Crops Research Institute for the Semi-Arid Tropics (ICRISAT)",
          profil:
            "Organisation à but non lucratif et apolitique qui mène des recherches agricoles pour le développement en Asie et en Afrique subsaharienne avec un large éventail de partenaires dans le monde entier.",
          image: "icrisat-logo-2016-new",
          site: "https://www.icrisat.org",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Industrie des Boissons du Sénégal (IBS)",
          profil:
            "Production et distribution de boissons gazeuses et de jus en canettes.",
          image: "Logo-IBS-2022-v2---400",
          site: "https://www.ibsenegal.com",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Institut De Technologie Alimentaire (ITA)",
          profil:
            "Institut de recherche-développement à voccation agroalimentaire.",
          image: "itaPlan-de-travail-1",
          site: "https://ita.sn/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Institut Sénégalais de Recherches Agricoles (ISRA)",
          profil:
            "Recherches  dans les domaines de production animales, végétales, forestières, halieutiques et socio-économiques.",
          image: "logo_isra-header-2021",
          site: "https://isra.sn/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "LE LIONCEAU",
          profil:
            "Alimentation et nutrition infantile.",
          image: "logo-lelionceau-mobile",
          site: "https://www.le-lionceau.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Louis Dreyfus Company Sénégal",
          profil:
            "Négociant et transformateur de produits agricoles.",
          image: "ldc",
          site: "https://www.ldc.com",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Mamelles Jaboot",
          profil:
            "Transformation et  commercialisation de produits laitiers.",
          image: "mamellesjaboot",
          site: "http://www.mamellesjaboot.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "NESTLE",
          profil:
            "Entreprise d'alimentation et de boissons au monde.",
          image: "nestle",
          site: "https://www.nestle.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Nouvelle Compagnie d’Import-Export (NOCIMEX)",
          profil:
            "Importation et  distribution de produits alimentaires,Présent en Guinée, Mali, Mauritanie, Gambie, Cameroun et Bénin.",
          image: "nocimex",
          site: "http://www.nocimex.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Nouvelle Minoterie Africaine (NMA)",
          profil:
            "Produits de nutrition humaine et animale.",
          image: "nmasanders",
          site: "https://nmasanders.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Olam Sénégal SA",
          profil:
            "Alimentation et  fourniture d’ingrédients alimentaires, d’aliments pour animaux et de fibres à des milliers de clients dans le monde entier.",
          image: "olam-logo-new",
          site: "https://www.olamgroup.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "PATISEN",
          profil:
            "Négoce, production et distribution de produits alimentaires, plus de 50 marques de produits présentes dans plus de 35 pays en Afrique et ailleurs, consommés du petit-déjeuner au dîner.",
          image: "LOGO-PATISEN-YOK-002",
          site: "https://patisen.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Programme des Domaines Agricoles Communautaires (PRODAC)",
          profil:
            "Les DAC sont des pôles de compétitivité économique, des lieux d’insertion de jeunes (diplômés ou non) mais également de promoteurs privés désireux d’investir le secteur aussi bien dans ses activités de production que dans celles de transformation et de services. Le concept se veut procéder d’une double démarche : (i) création de pôles de compétitivités économiques et (ii) aménagements structurants, permettant la mise en valeur de grands domaines, allant de 1 000 à 5 000 ha.",
          image: "logo_prodac-1",
          site: "https://www.prodac.sn/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "SDC Holding",
          profil:
            "Distribution du riz et d'autres céréales, Commerce général, importation du riz dans le monde entier,et des Engrais, Représentation commerciale, présent au Sénégal, au Mali, en Guinée Conakry, en Guinée Bissau et en Côte d'Ivoire.",
          image: "index_022",
          site: "https://www.sdcholding.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Sedima",
          profil:
            "Secteur avicole, Agro-business, Minoterie et Immobilier.",
          image: "Sedimapoulet",
          site: "https://www.linkedin.com/company/sedima-group/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "SEN LAMDAM TRADING (SLT)",
          profil:
            "Entreprise agroalimentaire évoluant dans la commercialistaion du sel.",
          image: "lamdam",
          site: "https://www.linkedin.com/in/sen-lamdam-trading-7061b2217/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Sénégal Progresse",
          profil:
            "Commercialisation de fruits et légumes provenant du Sénégal et du monde aussi conventionnel que Bio , Fournisseur des supermarchés et grandes surfaces sénégalaises: Auchan,Carrefour Market, Supeco, Senchan, Senteranga,Casino, Elydia,Sedicom.",
          image: "progresse",
          site: "https://senegalprogresse.com/fr/",
        },

        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Sénégalaise Industrie et Commerce (SENICO)",
          profil:
            "une industrie agroalimentaire de premier ordre qui produit et conditionne et commercialise ses propres marques.",
          image: "LOGO-SENICO",
          site: "https://senico-sa.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Socas",
          profil:
            "Production de concentré de tomates.",
          image: "Capture9",
          site: "https://www.socas-senegal.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Société Africaine de Produits Laitiers (Saprolait)",
          profil:
            "Industrie laitière.",
          image: "saprolait-logo",
          site: "https://www.saprolait.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Société de Développement Agricole et Industriel (SODAGRI)",
          profil:
            "Société placée sous la tutelle technique du ministère de l'agriculture avec un objectif large de promotion des projets agricoles, industriels et d'infrastructures à l'intérieur du Sénégal.",
          image: "logo_nexpages",
          site: "https://www.nexpages.com/sn/societe-de-developpement-agricole-et-industriel-sodagri-senegal-4971",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Société de pêche et d'armement sénégalais - Sopasen",
          profil:
            "Société de pêche industrielle,Exportation de produits de la mer frais et congelés.",
          image: "f645b22a40aab32f22b4524384cd46",
          site: "https://www.au-senegal.com/sopasen,5111.html",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Société des Brasseries de l’Ouest-Africain(SOBOA)",
          profil:
            "Filiale du Groupe Castel, intervenant dans le secteur agroalimentaire à travers la production et la commercialisation des boissons gazeuses et bières ainsi que le négoce de vins fins.",
          image: "cropped-cropped-logo-soboa-1",
          site: "https://soboa.sn/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Sociétè d'exportation des produits agricoles et maraîchers (Sepam)",
          profil:
            "Entreprise Agro-industrielle spécialisée dans la production de fruits et légumes frais pour le marché local, les pays limitrophes et les exportations vers l’Europe.",
          image: "logo_small_1451489293",
          site: "http://www.sepamsn.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Société Industrielle de chocolat (SICO)",
          profil:
            "Production de pate à tartiner chocolatée, de barquettes de chocolat, de mayonnaise et de boissons sucrées.",
          image: "logo-senpages-550x550-1-550x550",
          site: "https://www.senpages.com/entreprise/sico-societe-industrielle-de-chocolat/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "SODEFITEX",
          profil:
            "Agro-industrie cotonnière.",
          image: "LOGO-SODEFITEX-",
          site: "https://sodefitex.sn",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "SOFIEX",
          profil:
            "Société spécialisée dans l’importation et la distribution de produits agroalimentaires au Sénégal, leader incontesté dans le secteur des produits et dérivés laitiers.",
          image: "sofiex-logo",
          site: "https://www.sofiex.sn",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Sogepal",
          profil:
            "Entreprise spécialisée dans la fabrication, la distribution, et la commercialisation de biscuits de types divers.",
          image: "Logo-Bisko_195x100",
          site: "https://bisko.sn/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "SOLEVO Sénégal",
          profil:
            "Société fournissant des solutions globales et durables aux agriculteurs et aux industries, Des engrais aux semences et produits de protection des cultures, nous ne fournissons que des produits de qualité, incluant notre célèbre marque « La Cigogne ».",
          image: "logo-solevo@2x",
          site: "https://www.solevogroup.com/fr/solevo-senegal/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Sonacos SA/Ex Suneor",
          profil:
            "Production d'huile brute et de tourteaux et distrubition de produits alimentaires.",
          image: "SONACOS",
          site: "https://www.sonacos.sn/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Sosagrin",
          profil:
            "Production et distribution de moutardes, vinaigre, piment et autres sauces.",
          image: "Logo-Lys",
          site: "https://www.sosagrin.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "TAKAMOUL FOOD SA",
          profil:
            "Production, transformation et commercialisation de la tomate double concentré, ketchup et vinaigre.",
          image: "logo-senpages-550x550-1-550x550",
          site: "https://www.senpages.com/entreprise/takamoul-food-sa/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Van Oers United Sarl Sénégal/Filiale du Groupe Primeale United",
          profil:
            "Distribution internationale, Production et Exportation de fruits et légumes.",
          image: "540bd6690a6589c800abc8bdbb4613",
          site: "https://au-senegal.com/van-oers-senegal-sarl,4895.html?lang=fr",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Zena Exotic Fruits",
          profil:
            "Transformation de fruits et légumes.",
          image: "zenaLogo",
          site: "https://www.zenaexoticfruits.com",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Agence d'Exécution Travaux d'Intérêt Public (AGETIP)",
          profil:
            "Agence ayant pour but au Sénégal, d’engager toute action en vue de l’augmentation à court terme de la demande en matière de travaux publics et la création l’emplois pour la main d’œuvre non qualifiée.",
          image: "cropped-TITRE4-1",
          site: "https://agetip.net/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Agts Groupe",
          profil:
            "Geotechnics, Geophysics, Soil Laboratory,Topography, Mining.",
          image: "apave_new",
          site: "http://www.agtsgroupe.com",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Alpages",
          profil:
            "Contrôle technique et réglementaire.",
          image: "neologo",
          site: "https://groupe-alpages.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Arezki Group",
          profil:
            "Entreprise de construction exerceant des activités dans divers domaines de l'infrastructure en Afrique de l'Ouest depuis plus de 60 ans.",
          image: "Arezki-official-logo-p-500",
          site: "http://arezkigroup.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Axiome Group",
          profil:
            "Le groupe d’entreprises Axiome a été créé en 2001 dans le cadre de développement des projets de construction. A nos jours nous possedons une grande experience et un personnel hautement qualifie dans la réalisation des projets dans tous les domaines de construction et nous sommes présents dans plusieurs pays de l’Europe et de l’Afrique.",
          image: "axiome.group",
          site: "http://axiome.group/",
        },

        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Batix",
          profil:
            "Installations industrielles, de bureaux, de façades, d’immeubles hauts standings.",
          image: "logo-batix-2",
          site: "https://batix.sn/en/home/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "BTP Consultance Contrôle Inspection",
          profil:
            "Contrôle technique dans le secteur du BTP.",
          image: "01-Logo-BCCI_BTP_def",
          site: "https://www.bcci-sn.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Bureau d'Etudes des Travaux Publics (BETP)",
          profil:
            "Etudes des travaux, bâtiments et constructions mettaliques et voieries.",
          image: "logo_nexpages",
          site: "https://www.nexpages.com/sn/bureau-d-etudes-des-travaux-publics-betp-senegal-3411",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Camacho Enghenaria",
          profil:
            "Entreprise spécialisée dans l'exécution de tout type d'infrastructures de génie civil et travaux publics tout particulièrement sur les secteurs de l’eau et de l’environnement, de l’urbanisme, des voies de communication et des aménagements extérieurs, ainsi que sur la réhabilitation urbaine et hydroagricole.",
          image: "",
          site: "https://rodriguescamacho.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Compagnie Sahélienne d’Entreprises (Groupe CSE)",
          profil:
            "Spécialisée dans les BTP, routes, terrassements et ouvrages d’art, bâtiment et génie civil, hydraulique et assainissement.La CSE s’est imposée comme une entreprise incontournable dans le secteur des travaux publics et du bâtiment au Sénégal et dans la sous-région Ouest Africaine.",
          image: "WhatsApp-Image-2020-05-15-at-17.13.00",
          site: "https://groupecse.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Concept Bâtiment Sénégal(CBS)",
          profil:
            "Entreprise générale de bâtiment ayant comme principales activités le gros oeuvre et le second œuvre et réalisant aussi bien des travaux neufs, que des travaux de réhabilitations.",
          image: "wall",
          site: "https://cbs.sn/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Consortium d'Entreprises (CDE AFRICA)",
          profil:
            "Entreprise de référence spécialisée dans le domaine du Bâtiments et des Travaux Publics avec la réalisation d’ouvrages prestigieux au Sénégal, en Afrique de l’ouest, en Afrique centrale et au Moyen-Orient.",
          image: "logo-cde2x",
          site: "https://www.cde.africa/fr/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Consortium Immobilier",
          profil:
            "Développement de programmes immobiliers, le secteur logements sociaux et logements de standing.",
          image: "27799dc1780669a42193080e3199c3",
          site: "https://au-senegal.com/consortium-immobilier,1481.html",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "CORI SARL",
          profil:
            "Etude, conception et construction générale de bâtiment.",
          image: "corisarl",
          site: "https://corisarl.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "DELTA SA",
          profil:
            "Assainissement et BTP.",
          image: "delta",
          site: "https://www.deltasa.sn/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Dima Groupe",
          profil:
            "Agence immobilière spécialisée dans la location et la vente d’appartements hauts de gamme.",
          image: "dimagroupe",
          site: "https://www.dimagroupe.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "DMCE International",
          profil:
            "Construction de bâtiments, de routes et d’ouvrage d’art.",
          image: "dmceinternational",
          site: "http://dmceinternational.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "EBATH",
          profil:
            "Btp & Voieries et Réseaux Divers (VRD), Espaces verts, Assainissements, Adductions d'eau.",
          image: "logo-senpages-550x550-1-550x550",
          site: "https://www.senpages.com/entreprise/ebath/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "EGB Badaracchi",
          profil:
            "Gros Oeuvre, Aménagements, Revêtements, Corps d'Etats Secondaires.",
          image: "badaracchi",
          site: "https://www.badaracchi.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "EIFFAGE CONCESSIONS",
          profil:
            "Bâtiment, Travaux publics, Route, Energie et  concessions.",
          image: "eiffage",
          site: "https://www.eiffage.sn",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "EIFFAGE GROUPE",
          profil:
            "Bâtiment, Travaux publics, Route, Energie et  concessions.",
          image: "eiffage",
          site: "https://www.eiffage.sn",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "EIFFAGE INFRASTRUCTURES",
          profil:
            "Bâtiment, Travaux publics, Route, Energie et  concessions.",
          image: "",
          site: "https://www.eiffage.sn",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "ENVOL IMMOBILIER",
          profil:
            "Société d’Ingénierie, de Conseil et de Management de projets dont les activités sont articulées autour des métiers de construction d’infrastructures d’État et de développement de projet immobiliers.",
          image: "envol-immo",
          site: "http://www.envol-immo.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Entreprise de Travaux Publics et de Bâtiment (ETPB)",
          profil:
            "Structure de travaux publique et de bâtiments. Elle collabore étroitement avec EIffage depuis sa création et a été impliqué dans presque toutes ses réalisations.",
          image: "8e329bd2f451c569bad04807b69356",
          site: "https://au-senegal.com/etpb-sa-entreprise-travaux-publics-et-batiments,5163.html?lang=fr",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "GENERALE D'ENTREPRISES (G.E)",
          profil:
            "Leader reconnu dans le domaine du bâtiment et du génie civil en Afrique. Elle s’inscrit dans une dynamique de croissance et de conquête de nouveaux marchés en proposant des ouvrages civils et industriels de haute performance embarquant les nouvelles technologies,garantissant la sécurité,les économies d'énergies et la protection de l'environnement.",
          image: "GE",
          site: "https://www.groupe-ge.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "GEOTEC AFRIQUE",
          profil:
            "Etudes des sols, reconnaissance minière, et ingénierie routière.",
          image: "geotec-afrique",
          site: "https://www.geotec-afrique.com",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Groupe Atepa Technologie",
          profil:
            "L’entreprise intervient dans le domaine de l’architecture, de la finance, des mines, de l’industrie, de l’énergie, de l’agrobusiness et des technologies.",
          image: "atepa",
          site: "http://www.atepa.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "INGEROP Afrique Ingénieurie",
          profil:
            "Bâtiment, eau, environnement, énergie.",
          image: "logo_eng",
          site: "https://www.ingerop.fr/en/news/senegal",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Kima Afrique",
          profil:
            "Entreprise spécialisée dans les grands travaux, il est un acteur majeur du BTP au Sénégal et en Afrique, et compte à son actif des centaines de réalisations.",
          image: "kimalogopret",
          site: "https://kimafrique.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "OBKmat Construction",
          profil:
            "Entreprise spécialisée dans les activités du bâtiment, des travaux publics, des travaux d’hydraulique, d’assainissement et dans la propreté urbaine.",
          image: "d1844e54029ef28483f2f0821bb489",
          site: "https://www.au-senegal.com/obkmat-construction,6290.html?lang=fr",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Ordre des architectes du Sénégal (ODAS)",
          profil:
            "Ordre des architectes est un établissement public à caractère professionnel, distinct des syndicats professionnels. Il est l’interprète des architectes auprès des pouvoirs publics et donne son avis sur la législation et la règlementation architecturale ainsi que sur toutes les questions intéressant l’architecture au sujet desquelles il est consulté par le gouvernement.",
          image: "customLogo",
          site: "https://sites.google.com/site/snarchitectes/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "PEACOCK",
          profil:
            " Filiale du groupe marocain Holmarcom, elle a pour vocation de participer à l’essor économique du pays via l’habitat social et a lancé son premier projet en 2014, dans la ville nouvelle de Diamniadio.",
          image: "Logo-Peacock-alou-2-1536x1536",
          site: "https://peacock-investment.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "PLASMA IMMO",
          profil:
            "Spécialisée dans les activités immobilières, elle a démarré un projet de construction de près de 400 logements à Diamniadio dans le germe de ville.",
          image: "Logo-plasma-re",
          site: "https://plasmaimmo.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "REALITES SENEGAL",
          profil:
            "Représente la seconde implantation du Groupe REALITES en Afrique et se donne comme créneau le développement de projets immobiliers et urbains à forte valeur ajoutée pour le territoire sénégalais.",
          image: "2000004952330",
          site: "https://www.realites-afrique.com/fr/qui-sommes-nous/realites-senegal/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "SABLUX",
          profil:
            "Un ensemble de quatre branches spécialisées dans l'achat, la vente et la gestion des propriétés. De l'acquisition des matériaux pour la construction, à l'exécution du chantier de construction, intégrant la gestion immobilière de votre propriété et son entretien.",
          image: "sabluxholding",
          site: "https://sabluxholding.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "SADIA Travaux BTP",
          profil:
            "L’entreprise SADIA joue un rôle d’intermédiation commerciale dans le domaine des BTP. Son rôle est de trouver les meilleurs collaborateurs lorsqu’on a un projet de construction de bâtiment ou d’infrastructure publique.",
          image: "logo-sadia-SenSys",
          site: "https://sadia-travaux.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Sahelia Construction",
          profil:
            "Entreprise de construction spécialisée dans le génie civil, aménagements intérieurs et extérieurs.",
          image: "siteon0-e5814",
          site: "https://www.sahelia-construction.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "SERTEM",
          profil:
            "SERTEM est devenu un acteur incontournable du secteur de l’immobilier passant rapidement du statut d’entrepreneur de BTP (Bâtiments et Travaux Publics) à celui de promoteur pour devenir le groupe qu’il est aujourd’hui.",
          image: "sertemgroupe",
          site: "https://www.sertemgroupe.com",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Siam Groupe",
          profil:
            "Entreprise de construction. Acteur du bâtiment et des infrastructures au Sénégal.",
          image: "logo-siam-2",
          site: "https://siam-groupe.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "SIGROUPE",
          profil:
            "Agence de location d'appartements meublés à distance meublé.",
          image: "logo-scroll",
          site: "http://www.sigroupe.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "SIPA SARL",
          profil:
            "Immobilier,Architecture, Ammeublement, Sanitaires.",
          image: "sipa",
          site: "https://www.sipasenegal.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "SISOL SA",
          profil:
            "L’installation d’une unité de production de panneaux pour la construction de bâtiments divers ; L’étude, l’expertise et l’ingénierie ; La consultance ; L’achat et la vente de biens immeubles; Le commerce général, l’importation et l’exportation.",
          image: "bce_logo",
          site: "https://creationdentreprise.sn/sisol-sa",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "SOCABEG",
          profil:
            "Entreprise sénégalaise de promotion immobilière et de btp, leader dans la réalisation de logement social au Sénégal.",
          image: "sbg",
          site: "http://socabeg.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Sociétè d'Equipement et de Construction (SOECO)",
          profil:
            "Entreprise spécialisée dans les activités du bâtiment, des travaux publics, des travaux d’hydraulique, d’assainissement, d'adduction d'eau, du concassage.",
          image: "soeco-logo",
          site: "https://soeco.sn/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "SOTRACOM SA",
          profil:
            "BTP,Aménagements Hydro-agricoles et Assainissement.",
          image: "stracosa",
          site: "http://www.sotracomsa.sn/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "STRUCTURE B SA",
          profil:
            "Promoteur immobilier,Constructeur,Consultant, Acteur de développement.",
          image: "SA_Plan",
          site: "https://www.structurebsa.com/",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Teyliom Sénégal",
          profil:
            "Groupe panafricain basé en Afrique subsaharienne avec une forte présence dans divers secteurs en Afrique de l’Ouest et du Centre tels que l’immobilier, l’hôtellerie, la finance, l’industrie et les télécommunications.",
          image: "cropped-teyliom_logo",
          site: "https://www.teyliom.com",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénieurie",
          nom: "Zeltex Sénégal SA",
          profil:
            "KALIA à pour objet le développement et la promotion immobilière, Vente immobilière avec travaux de construction.",
          image: "kalia_logo_horizontal1-1",
          site: "https://www.kalia.sn",
        },
        {
          secteur: "Services / Consultance",
          nom: "ABC Sénégal",
          profil:
            "Transactions commerciales, consultance, import-export.",
          image: "logo-senpages-550x550-1-550x550",
          site: "https://www.senpages.com/entreprise/abc-senegal/",
        },
        {
          secteur: "Services / Consultance",
          nom: "Adaptech Solutions Sénégal",
          profil:
            "Spécialisée dans la fourniture et l’installation d’unités de production clés en main (formation pratique et mise à disposition de l’outil de production), la consultance en entreprenariat et la mise en œuvre de projets d’insertion professionnelle par l’auto emploi pour les jeunes et les femmes exclusivement dans l’industrie de production ou de transformation.",
          image: "1519902337029",
          site: "https://www.linkedin.com/company/adaptech-solutions-senegal/",
        },
        {
          secteur: "Services / Consultance",
          nom: "ADOC Audit & Conseil",
          profil:
            "Cabinet d'expertise comptable et de conseil.",
          image: "ADOC-Senegal",
          site: "https://adoc-sn.com/",
        },
        {
          secteur: "Services / Consultance",
          nom: "Afrisecours",
          profil:
            "Sécurité dans les entreprises, premier secours, gestion des risques.",
          image: "logo-senpages-550x550-1-550x550",
          site: "https://www.senpages.com/entreprise/afrisecours/",
        },
        {
          secteur: "Services / Consultance",
          nom: "AME TRADE SENEGAL",
          profil:
            "Cabinet évenementiel B to B.",
          image: "ametrade-logo",
          site: "https://ametrade.org/",
        },
        {
          secteur: "Services / Consultance",
          nom: "Apave Sahel",
          profil:
            "Maitrise des risques en construction et infrastructures.",
          image: "ApaveLogo",
          site: "https://www.apave.com/fr-FR/",
        },
        {
          secteur: "Services / Consultance",
          nom: "Car Rapide Prestige",
          profil:
            "Service de livraison express et location de véhicules avec chauffeur privé.",
          image: "carrapideprestige-550x550-1",
          site: "https://www.senpages.com/entreprise/car-rapide-prestige/",
        },
        {
          secteur: "Services / Consultance",
          nom: "CCBM HOLDING",
          profil:
            "Automobile & Machinerie,Espace Hi-tech,Grande distribution,Logistiques & Services,Communication & Media.",
          image: "holding",
          site: "http://www.ccbm.sn/",
        },
        {
          secteur: "Services / Consultance",
          nom: "Centrale Equipements Sénégal",
          profil:
            "Distribution et installation d'équipements et matériels de cuisine.",
          image: "cropped-cropped-logo-central_Plan-de-travail-1",
          site: "https://centralequipements.com/",
        },
        {
          secteur: "Services / Consultance",
          nom: "Compagnie Africaine de Commerce (CAC)",
          profil:
            "Commercialisation de tous produits  de cuisine et accessoires de gaz, représentant de certaines grandes marques italiennes comme Foker.",
          image: "logo-site",
          site: "https://cacsenegal.com/",
        },
        {
          secteur: "Services / Consultance",
          nom: "CTA Sénégal",
          profil:
            "Distribution, Service et Commerce.",
          image: "ctagroup",
          site: "https://www.ctagroup.eu",
        },
        {
          secteur: "Services / Consultance",
          nom: "Deloitte",
          profil:
            "Cabinet d'Audit et conseil.",
          image: "Deloitte-Societe-davocats",
          site: "https://www2.deloitte.com/afrique/fr/footerlinks/deloitte-senegal.html",
        },
        {
          secteur: "Services / Consultance",
          nom: "Ernst & young",
          profil:
            "Audit comptable, Contrôle et Certification.",
          image: "ey",
          site: "https://www.ey.com/en_sn",
        },
        {
          secteur: "Services / Consultance",
          nom: "Fumoa Sénégal",
          profil:
            "Fabrication et commercialisation d'emballages métalliques(fûts) et plastiques(jirrycans, bidons, flacons, pots, bouteilles et préformes).",
          image: "2c518c54be9b1370172634537cfb39",
          site: "https://www.au-senegal.com/fumoa,4877.html",
        },
        {
          secteur: "Services / Consultance",
          nom: "GROUPE COSEMAD",
          profil:
            "Evolue principalement dans les domaines majeurs de la vie et du bien être humain, plus précisément dans l’alimentaire, le médical, l’immobilier et l’énergie.",
          image: "1537981341735-1",
          site: "https://www.cosemad.sn",
        },
        {
          secteur: "Services / Consultance",
          nom: "Groupe Ninki Pro Sécurité",
          profil:
            "Sécurité privé, protection rapprochée, sécurité évenementielle, immobilier (location et vente).",
          image: "305026869_473496911453706_6853308605348758786_n",
          site: "https://www.facebook.com/profile.php?id=100063802040162&mibextid=ZbWKwL",
        },
        {
          secteur: "Services / Consultance",
          nom: "Institut d’Etudes et d’Evaluations des Politiques Publiques et Stratégies (I2EPS)",
          profil:
            "Formation ( longue et courte durée), Recherche-publication, Evaluation des Politiques publiques, Stratégies et Cabinet de  Consultance juridique aux Etats et aux Entreprises.",
          image: "Sans-titre-15-300x300",
          site: "https://www.i2eps.com",
        },
        {
          secteur: "Services / Consultance",
          nom: "Kitchen Pro",
          profil:
            "Grossiste CHR :équipements hôtels, restaurants, bars, collectivités de A à Z ! Verrerie, art.",
          image: "205393751_647208832888279_4070251940491881405_n",
          site: "https://www.facebook.com/KitchenPROdakar/",
        },
        {
          secteur: "Services / Consultance",
          nom: "KPMG Sénégal",
          profil:
            "Leader de l'audit et du conseil, KPMG Sénégal est membre de KPMG International, réseau de cabinets indépendants exerçant dans 152 pays.",
          image: "kpmg-logo-2",
          site: "https://kpmg.com/sn/fr/home.html",
        },
        {
          secteur: "Services / Consultance",
          nom: "La Rochette",
          profil:
            "Studio Graphique et Industrie d’Impression présent au Sénégal, en Gambie, Mali, Mauritanie, Guinée, Gabon, Bénin.",
          image: "siteon0",
          site: "https://www.au-senegal.com/la-rochette,5125.html",
        },
        {
          secteur: "Services / Consultance",
          nom: "La Sénégalaise de l'intérim (Sen Intérim)",
          profil:
            "Sociétè de ressources humaines.",
          image: "cropped-cropped-telechargement-removebg-preview",
          site: "https://seninterim.sn/",
        },
        {
          secteur: "Services / Consultance",
          nom: "MANDARINE",
          profil:
            "un véritable outil multi-fonctions au service de la communication visuelle.Pré-presse, impression numérique, signalétique, objets publicitaires, cadeaux d’entreprises, etc.",
          image: "mandarine-sn",
          site: "https://www.mandarine-sn.com",
        },
        {
          secteur: "Services / Consultance",
          nom: "MINEKIP",
          profil:
            "Prestations de services dans les secteurs des Mines, Oil and Gas et BTP.",
          image: "LOGO-MINEKIP-RECTANGULAIRE-FOND-SOMBRE",
          site: "https://minekip.com/",
        },
        {
          secteur: "Services / Consultance",
          nom: "MULTIDIS",
          profil:
            "Distribution d’équipements de Grande Cuisine et de matériels pour le Froid commercial et industriel, Distributeur officiel de grandes marques européennes.",
          image: "siteon0-b26ee",
          site: "https://www.multidis-sn.com/",
        },
        {
          secteur: "Services / Consultance",
          nom: "SATLX IT SERVICES",
          profil:
            "Prestataire de services spécialisé dans les solutions et matériels informatiques, les réseaux et les télécommunications / VSAT, Présent au Sénégal, à Bamako et en France, intevention dans plusieurs pays africains.",
          image: "satlex",
          site: "https://satlx.net/",
        },
        {
          secteur: "Services / Consultance",
          nom: "SEHMS",
          profil:
            "Cabinet d’étude, de conseil, d’audit et de formation.",
          image: "LOGO-e1650469039822",
          site: "https://sehms-sn.com/",
        },
        {
          secteur: "Services / Consultance",
          nom: "SenOsteo",
          profil:
            "Osteopathic Manipulative Therapy.",
          image: "enOsteo",
          site: "https://www.SenOsteo.com",
        },
        {
          secteur: "Services / Consultance",
          nom: "Services Environnement Technologies (SENTECH)",
          profil:
            "Sociétè spécialisée en Protection de l’Environnement et Maîtrise des Risques offrant à ses clients des conseils et prestations de services.",
          image: "sentechlogo",
          site: "https://www.sentechsn.com/",
        },
        {
          secteur: "Services / Consultance",
          nom: "Société Civile Professionnelle Patricia Lake Diop & Djibril Thiam Notaires associés",
          profil:
            "Cabinet notarial.",
          image: "logo-senpages-550x550-1-550x550",
          site: "https://www.senpages.com/entreprise/etudes-maitre-patricia-lake-diop-et-djibril-thiam/",
        },
        {
          secteur: "Services / Consultance",
          nom: "SOCIUM JOB",
          profil:
            "Sociétè de ressources humaines, présent au Sénégal, au Mali, en Mauritanie, en Gambie, en Guinée Bissau, en Guinée Conakry, au Burkina Faso; au Niger.",
          image: "socium",
          site: "https://sociumjob.com/",
        },
        {
          secteur: "Services / Consultance",
          nom: "SOJUFISC",
          profil:
            "Conseil juridique et fiscal.",
          image: "logo_sojufisc_Plan-de-travail-1-copie-2",
          site: "https://www.sojufisc.com",
        },
        {
          secteur: "ICT et électronique",
          nom: "Ams technologies",
          profil:
            "AMS Technologies propose une gamme de solutions à forte valeur ajoutée, aux organisations : entreprises privées, publiques et administration ; pour gérer l’accueil, les flux de personnes quel que soient leur nombre et leur taille ; et faciliter leur orientation grâce la gestion électronique des files d’attente de personnes (visiteurs, clients, patients, etc…).",
          image: "5b2f73b5f1160",
          site: "http://www.amstechnologies.net/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Arc informatique",
          profil:
            "Le Groupe ARC, c’est plus de 60 collaborateurs répartis au Sénégal et au Mali au service de la région Ouest-Africaine, prêts à vous servir à travers:ARC As A Service pour les services managés -ARC Solutions pour les solutions informatiques et télécoms- ARC Shop pour la fourniture d’équipements- ARC Telecom pour la Fourniture d’Accès Internet- ARCCelerate un programme d’accélération de croissance de startups évoluant dans les technologies.",
          image: "Logo-Arc-70",
          site: "https://site.arc.sn/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Autorité de régulation des télécoms_ ARTP",
          profil:
            "L’Autorité de Régulation des Télécommunications et des Postes, en abrégé « ARTP », est créée, auprès du Président de la République, en tant qu’autorité administrative indépendante, chargée de réguler les secteurs des télécommunications et des postes. L’ARTP est dotée de la personnalité juridique et de l’autonomie financière et de gestion.",
          image: "artp",
          site: "https://artp.sn/lartp/nos-missions",
        },
        {
          secteur: "ICT et électronique",
          nom: "Canal+ Sénégal",
          profil:
            "Leader de l'édition et de la distribution de bouquets de chaînes télévisées francophones.",
          image: "f2ee77d5da0744b8aa265c0aa618f1ccb04c9874",
          site: "https://www.canalplus-afrique.com/sn/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Cfao technologies",
          profil:
            "Forts d’une expertise dans 3 activités – ICT (Information & Communication Technologies) et Cybersécurité, Lift et Energie – et d’un siège sur le continent (Abidjan), nous proposons aux entreprises et organisations des secteurs privés et publics des services performants et innovants. Notre ambition : contribuer à la transition énergétique et digitale de nos clients en Afrique.",
          image: "cfao",
          site: "https://www.cfaogroup.com/fr/infrastructure/cfao-technology-energy/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Comtel ingénierie",
          profil:
            "COMTEL INGENIERIE (ingénierie et management des systèmes technologiques_services) s'emploie avec ses solutions, à protéger l'intégrité des personnes, des biens et la pérennité de vos activités.Elle propose des systèmes de sécurité électronique sur-mesure, capables de répondre aux besoins des clients les plus exigeants, par la parfaite maîtrise du cycle de vie de vos installations.",
          image: "fa1338_4f43ab3c15e842eb8d5dc2742a3a278c_mv2",
          site: "https://www.comtelingenierie.com/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Ctic dakar",
          profil:
            "CTIC Dakar, hub leader d’entrepreneuriat numérique en Afrique de l’Ouest francophone à l’horizon 2025.",
          image: "Logo-CTIC",
          site: "https://www.cticdakar.com/",
        },
        {
          secteur: "ICT et électronique",
          nom: "DSTV Sénégal",
          profil:
            "Service de télévision numérique par satellite de la compagnie Sud-Africaine, Multichoice qui offre à ses abonnés, à travers l'Afrique, une large gamme de chaînes de télévision payante en Anglais mais aussi des chaînes Indiennes, Chinoises et des chaînes Françaises en option.",
          image: "",
          site: "https://www.linkedin.com/company/astv-s%C3%A9n%C3%A9gal/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Emc2",
          profil:
            "Société senegalaise créée par des jeunes ingénieurs et chercheurs de plusieurs nationalités qui ont pour ambition de mettre à la disposition des clients les dernières technologies de l'information et de la communication.",
          image: "emc",
          site: "https://www.emc2-group.com/index.php?option=com_contact&view=contact&id=1&Itemid=41&8c15555a4e9cf3756498934ba83b733a=bbb185eb838c244018e19b782a6f2bd7",
        },
        {
          secteur: "ICT et électronique",
          nom: "GBHT",
          profil:
            "GBHT est une Entreprise de Services du Numérique (ESN) créée en Juin 2007. Notre gamme de produits et services permet de répondre aux besoins professionnels des entreprises tels que le Conseil en Management Technique, la MOA / AMOA, le Conseil / Audit, le Développement et l'exploitation des Applications de Gestion et de Gouvernance, l’Intégration, la Tierce Maintenance Applicative, la formation pour les entreprises et administrations etc.",
          image: "",
          site: "https://www.linkedin.com/company/gbht-s%C3%A9n%C3%A9gal-sarl/about/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Groupe Chaka",
          profil:
            "Le Groupe Chaka, acteur international des technologies de l’information et de la communication, fournit aux entreprises africaines et à ses clients du monde entier des solutions informatiques novatrices à forte valeur ajoutée.",
          image: "chaka",
          site: "http://www.groupechaka.com/-Le-Groupe-.html?lang=fr",
        },
        {
          secteur: "ICT et électronique",
          nom: "Groupe E-Media Invest SA",
          profil:
            "Une marque de presse qui se donne à lire, à écouter et à voir avec la plus grande variété possible.",
          image: "emdia",
          site: "https://www.emedia.sn",
        },
        {
          secteur: "ICT et électronique",
          nom: "Groupe Excaf Télécom",
          profil:
            "Opérateur audiovisuel : Réseau Tnt-Rdv-Dtv-Radios.",
          image: "",
          site: "https://www.linkedin.com/company/groupe-excaf-t%C3%A9l%C3%A9com/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Groupe Futurs Médias (GFM)",
          profil:
            "Groupe de presse.",
          image: "",
          site: "https://gfm.sn/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Groupe Origines SA",
          profil:
            "Société anonyme de droit sénégalais spécialisée dans la production audiovisuelle.",
          image: "",
          site: "https://2stv.net/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Groupe Walfadjri",
          profil:
            "Groupe de presse.",
          image: "",
          site: "http://www.walf-groupe.com/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Gsie technology",
          profil:
            "Fort de plus d’une vingtaine d’années d’expertise dans des domaines aussi divers et variés que la conception et l’intégration de solutions, l’agrégation de services à valeur ajoutée, le Conseil en SI.",
          image: "",
          site: "https://gsietechnology.com/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Hayo",
          profil:
            "Opérateur télécom.",
          image: "",
          site: "https://www.hayo.sn",
        },
        {
          secteur: "ICT et électronique",
          nom: "Itech Afrique",
          profil:
            "ITECH Solutions est un Centre de Compétence SAGE (PME, MGE), le plus haut niveau de certification de l'Editeur SAGE. Présent dans six pays en Afrique.",
          image: "",
          site: "https://itechafrique.com/contact-corporate/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Manobi Africa",
          profil:
            "Fournisseur de solutions et de services numériques pour les entreprises, les projets de développement et les prestataires de services dans les secteurs de l'eau et de l'agriculture en Afrique, présent dans 14 pays africains.",
          image: "",
          site: "https://www.manobi.com/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Ndak Tech",
          profil:
            "Distributeur et intégrateur de solutions dans les domaines de la sécurité électronique, du contrôle à distance et des réseaux informatiques.",
          image: "",
          site: "https://www.ndaktech.com/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Neurotech",
          profil:
            "Opérateur Panafricain de Services Informatiques et de Talents.",
          image: "",
          site: "https://www.groupeneurotech.com",
        },
        {
          secteur: "ICT et électronique",
          nom: "Oumou Lde",
          profil:
            "Société spécialisée en ingénierie et solutions informatiques dédiés aux entreprises.",
          image: "",
          site: "https://www.oumouinformatique.com",
        },
        {
          secteur: "ICT et électronique",
          nom: "Orange Sonatel/Direction des Entreprises",
          profil:
            "Opérateur téléphonique.",
          image: "",
          site: "https://sonatel.sn/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Platform technologies sa",
          profil:
            "Société évoluant principalement dans le domaine des Nouvelles Technologies de l’Information et des Communications.",
          image: "",
          site: "https://www.platform.sn",
        },
        {
          secteur: "ICT et électronique",
          nom: "Regiosis",
          profil:
            "Entreprise de services numérique REGIOSIS fournis des services de Haute Technologie, des solutions de conseils, d’intégration des systèmes, d’infogérance et la formation.Partenaire de grands éditeurs et constructeurs en IT & Telcom, ESN REGIOSIS est une entreprise orientée «Service Ingénierie» propose tout un panel de solutions dans des domaines précis avec une parfaite maitrise et un savoir-faire éprouvé .",
          image: "",
          site: "https://www.regiosis.com/#about-bar",
        },
        {
          secteur: "ICT et électronique",
          nom: "Sesam informatics",
          profil:
            "Sesam informatics, société de droit sénégalais a été créée en 2006 par un ingénieur certifié CCIE Cisco issu du métier de l’intégration et de la distribution informatique IT.Avec une spécialisation dans l’intégration, la sécurité et la convergence d’infrastructures réseaux et télécoms, Sesam informatics se démarque sur le marché sénégalais et sous-régional de par son large portefeuille de services et maitrise des technologies innovantes.",
          image: "",
          site: "https://www.sesam-informatics.com/a-propos/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Société de Télédiffusion du Sénégal (TDS SA)",
          profil:
            "Société assurant la fonction d’opérateur de diffusion national et en ce sens prend en charge la collecte, le multiplexage et le transport, puis la diffusion des contenus audiovisuels par voie numérique dans les foyers sénégalais.",
          image: "",
          site: "https://www.tds.sn/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Socitech",
          profil:
            "Société panafricaine d'intégration de solutions informatiques.",
          image: "",
          site: "htps://www.socitech.com ",
        },
        {
          secteur: "ICT et électronique",
          nom: "Sénégal Numérique Sa",
          profil:
            "L’Agence de l’informatique de l’Etat (ADIE) qui s’appelle maintenant Sénégal Numérique est l’acteur principal au Sénégal chargé de mettre en œuvre la politique d’informatisation de l’Etat ainsi que la gestion des infrastructures numériques de l'État.",
          image: "",
          site: "https://www.adie.sn",
        },
        {
          secteur: "ICT et électronique",
          nom: "SOFNORTECH",
          profil:
            "Entreprise spécialisée dans les technologies numériques.",
          image: "",
          site: "https://www.sofnortech.com/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Solarcom",
          profil:
            "Le Groupe SFEE SOLARCOM AFRIQUE est spécialisé dans la vente, l'installation, la maintenance et le service après vente d'ateliers d'énergie pour les opérateurs télécoms.",
          image: "",
          site: "https://www.sfeesolarcomafrique.com/activit%C3%A9s-expertise",
        },
        {
          secteur: "ICT et électronique",
          nom: "Solid Afrique",
          profil:
            "SOLID Afrique offre une gamme de services et de solutions qui couvrent tous les besoins informatiques des entreprises d'aujourd'hui. Nous soutenons les grandes entreprises et les petites entreprises dans les choix les plus appropriés pour leur système d'information.",
          image: "",
          site: "https://www.solid.sn/a-propos-de/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Sylamtech Groupe",
          profil:
            "Une société de droit sénégalais évoluant dans la distribution de solutions IT. Leader dans le domaine et distributeur officiel dans toute la zone de l’Afrique de l’Ouest Francophone, nous proposons de grandes marques dans les domaines aussi divers que variés de la vidéoconférence, de la téléphonie sur IP, du network equipments etc.",
          image: "",
          site: "https://www.sylamtechgroup.com/a-propos/",
        },
        {
          secteur: "ICT et électronique",
          nom: "TRIGGER'S REPORTS",
          profil:
            "Application de sécurité et de géolocalisation.",
          image: "",
          site: "https://triggersreports.com/",
        },
        {
          secteur: "ICT et électronique",
          nom: "XperBM",
          profil:
            "Intégrateur de solutions informatiques.",
          image: "",
          site: "https://xperbm.com/contact/",
        },
        {
          secteur: "ICT et électronique",
          nom: "Zénith international",
          profil:
            "ZENITH INTERNATIONAL Audit et Conseil couvre actuellement les pays membres de l’Organisation pour l’Harmonisation du Droit des Affaires (OHADA), de l’Afrique de l’Ouest et du Centre.La structure est composée d’une équipe d’experts, d’ingénieurs, de consultants fonctionnels disposant d’un haut niveau de compétences logiciel & métier, d’informaticiens, de techniciens et de développeurs.",
          image: "",
          site: "https://www.ziac.sn/qui-sommes-nous/",
        },
        {
          secteur: "ICT et électronique",
          nom: "2D Business consulting",
          profil:
            "Editeur de logiciels de gestion financière, comptable et technique pour les organisations de types entreprises, ministère.",
          image: "",
          site: "https://2dbc.com/nos-services/",
        },

        {
          secteur: "Transport et logistique",
          nom: "Afrety",
          profil:
            "Société spécialisée dans le transport par voie aérienne ou maritime de tous biens vers et depuis l’Afrique.",
          image: "",
          site: "https://www.afrety.com/",
        },
        {
          secteur: "Transport et logistique",
          nom: "ALFAT CARGO",
          profil:
            "Société internationale implantée à Dakar, offrant des services de transport de fret aérien taillés sur mesure destinés aux entreprises aux transitaires et particuliers de l’Afrique de l'Ouest.",
          image: "",
          site: "https://alfatcargo.net/",
        },
        {
          secteur: "Transport et logistique",
          nom: "ATI (AIR TRANS INTERNATIONAL)",
          profil:
            "Entreprise de transport logistique spécialisée dans les domaines: Transit, Transport, Manutention, Consignation.",
          image: "",
          site: "https://www.senpages.com/entreprise/ati-air-trans-international/",
        },
        {
          secteur: "Transport et logistique",
          nom: "Bolloré Transports & Logistics Sénégal",
          profil:
            "Opérateur majeur du transport et de la logistique à l’international avec 35 000 collaborateurs, répartis dans 109 pays et sur les cinq continents.",
          image: "",
          site: "https://www.bollore-transport-logistics.com/",
        },
        {
          secteur: "Transport et logistique",
          nom: "BOLUDA",
          profil:
            "Spécialiste du transport intégral de marchandises et leader des services logistiques portuaires, Remorquage portuaire-Assistance en mer.",
          image: "",
          site: "https://www.boluda.com.es/fr/boluda-lines-fr/",
        },
        {
          secteur: "Transport et logistique",
          nom: "Centre de Groupage Fret Express (CGFE)",
          profil:
            "Société spécialisée dans le transport par groupage maritime au Sénégal.",
          image: "",
          site: "http://www.cgfe-groupage.com/",
        },
        {
          secteur: "Transport et logistique",
          nom: "CEVA LOGISTICS",
          profil:
            "Logistique et  Fret.",
          image: "",
          site: "https://www.cevalogistics.com",
        },
        {
          secteur: "Transport et logistique",
          nom: "CMA CGM Sénégal",
          profil:
            "Transport de marchandises en conteneurs par voie maritime et terrestre.",
          image: "",
          site: "https://www.cma-cgm.fr/local/senegal",
        },
        {
          secteur: "Transport et logistique",
          nom: "Compagnie Sénégalaise de Transports Transatlantiques-Afrique de l'Ouest (CSTT)",
          profil:
            "Fourniture de services logistiques personnalisés et de qualité.",
          image: "",
          site: "https://www.csttao.com",
        },
        {
          secteur: "Transport et logistique",
          nom: "DHL",
          profil:
            "Entreprise proposant des solutions logistiques.",
          image: "",
          site: "https://www.dhl.com/sn-fr/home.html",
        },
        {
          secteur: "Transport et logistique",
          nom: "DP World (Dubaï Port World)",
          profil:
            "Principal fournisseur de solutions logistiques intelligentes, permettant le flux des échanges commerciaux à travers le monde.",
          image: "",
          site: "https://www.dpworld.com/",
        },

        {
          secteur: "Transport et logistique",
          nom: "Entreprise Africaine de Transit et de Transport(EATT)",
          profil:
            "Entreprise spécialisée dans le transit et dédouanement, l'expédition et l'exportation de toutes marchandises ou produits par voie maritime, aérien, ferroviaire ou routière, et sur toutes destinations.",
          image: "",
          site: "https://eatt.business.site/",
        },
        {
          secteur: "Transport et logistique",
          nom: "Flying Wings",
          profil:
            "Transport routier de marchandises et matières premières.",
          image: "",
          site: "https://www.flyingwingsn.com/",
        },
        {
          secteur: "Transport et logistique",
          nom: "Sea-Invest Sénégal",
          profil:
            "SEA-invest est un des principaux opérateurs de terminaux au monde pour le vrac sec, breakbulk, les fruits et le vrac liquide.Le groupe jouit actuellement d’une renommée mondiale dans les domaines de la manutention, de l’entreposage et d’autres activités portuaires.",
          image: "",
          site: "https://www.sea-invest.com",
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Africaine de Chaudronnerie et de Tuyauterie SA (ACT Sénégal)",
          profil:
            "Spécialisée dans tout ce qui est conception, fabrication et maintenance industrielle dans les domaines de la chaudronnerie, de la tôlerie et de la tuyauterie.",
          image: "",
          site: "https://www.act-sn.com/",
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Aluminium du Sénégal (ADS)",
          profil: "Fourniture matériel de construction et bricolage.",
          image: "",
          site: "https://www.nexpages.com/sn/aluminium-du-senegal-ads-senegal-4725",
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Batec",
          profil: "Une équipe d'hommes et de femmes tous experts faisant référence dans leurs domaines de compétences  offrant des services pour vos constructions en second œuvre concernant l'aluminium,la cuisine, la salle de bains, le placoplatre,le vitrage, les adjuvants,les façades ventilées,le matériel de chantier!",
          image: "",
          site: "https://www.batecsenegal.com/",
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "BATFUTUR",
          profil: "Société industrielle spécialisée dans la production d'armatures GFRP, des matériaux de construction innovants, respectueux de l’environnement et économiques.",
          image: "",
          site: "http://batfutur.com/",
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "CDS Les Ciments du Sahel",
          profil: "Cimenterie,carrières et granulats.",
          image: "",
          site: "https://www.nexpages.com/sn/ciments-du-sahel-senegal-643",
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Comptoir Commercial Plomberie du Sénégal(CCPS)",
          profil: "Spécialisée dans l’importation, la distribution des sanitaires, de la plomberie, industrie, pompe et matériel d’irrigation.",
          image: "",
          site: "https://au-senegal.com/ccps-comptoir-commercial-de-plomberie-du-senegal,6161.html?lang=fr",
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Comptoir commercial du Sénégal (CCS)",
          profil: "Import-export de matériaux de construction: plomberie, sanitaire, carrelage, marbre et granit.",
          image: "",
          site: "https://au-senegal.com/ccs-comptoir-commercial-du-senegal,4092.html"
        },

        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "CP Matériaux",
          profil: "Distribution de des matériaux et fournitures pour le bâtiment : étanchéité, isolants, géosynthétique, panneaux, sols, revêtements.",
          image: "",
          site: "https://www.cp-materiaux.com"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "CSE GRANULATS",
          profil: "Production de granulats et transport.",
          image: "",
          site: "https://csegranulats.sn/"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "DANGOTE CEMENT SENEGAL S.A",
          profil: "Producteur de ciment en Afrique avec des opérations existantes dans 10 pays africains.",
          image: "",
          site: "https://www.dangotecement.com"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "DHS / Delta Holding Sénégal",
          profil: "Galvanisation à Chaud, Candélabre d’Eclairage Publique, Armement de Lignes Electriques, Peinture Routière, distribution de bitumes.",
          image: "",
          site: "https://au-senegal.com/dhs-delta-holding-senegal,5153.html"
        },

        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "DMC Sénégal(Metalco est le showroom)/Filiale du Groupe METAL",
          profil: "Le fer est son cœur de métier allant du petit outillage aux grandes machines, propose une solution plus large pour les métiers du BTP, des industries, des mines et carrières, du garage, des pétroliers.",
          image: "",
          site: "https://www.dmcsen.com"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "EBI Sénégal",
          profil: "Fabrication de matériaux de construction: agglos béton, pavés.",
          image: "",
          site: "https://ebisenegal.business.site/"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "GROUPE BÂTIMAT",
          profil: "Distribution de matériaux de construction et de produits sidérurgiques en Afrique, présent dans 11 pays.",
          image: "",
          site: "https://www.linkedin.com/company/groupe-batimat/about/"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "HOLDING KEUR KHADIM (HKK)",
          profil: "Fourniture matériel de construction et bricolage.",
          image: "",
          site: "https://www.nexpages.com/sn/holding-keur-khadim-hkk-senegal-4940"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "LASSARAT RENOV",
          profil: " Construction métallique, tuyauterie, chaudronnerie, montage mécanique, Location d’Échafaudages, Sablage Peinture industrielle.",
          image: "",
          site: "https://www.dnb.com/business-directory/company-profiles.lassarat_renov_senegal.a59df62b9d647de4c20154895e95b6b7.html"
        },

        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Les Ateliers du Sahel (LAS)",
          profil: "Spécialistes des Grands Travaux en Metallurgie.",
          image: "",
          site: "http://www.ateliers-sahel.com/"
        },

        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Megabat",
          profil: "Spécialiste de la création et de l’installation de cuisines équipées (modernes ou classiques), de chambres à coucher, dressings et rangements fonctionnels, de meubles TV ou encore de bureaux, de portes, de meubles de réception, de salle de bain et bien plus….",
          image: "",
          site: "https://www.megabatsenegal.com/"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "OBBO Sénégal",
          profil: "Ammeublement et décoration.",
          image: "",
          site: "https://www.senpages.com/entreprise/obbo-senegal/"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Prisma Industries Showroom Mermoz (Sénégal)",
          profil: " Fabricant sénégalais de peinture. Prisma possède son propre laboratoire de recherche et développement. Avec une unité de production ayant une capacité de 5000 tonnes par an, Prisma peut promouvoir l’innovation, avec  une gamme de peintures plus propres, plus saines et en conformité avec  toutes les réglementations internationales.",
          image: "",
          site: "https://www.prismaindustries.sn/"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "RASSOUL BUILDING",
          profil: "Spécialisée dans la commercialisation et la mise en oeuvre des produits du second œuvre du bâtiment dont les carreaux, appareils sanitaires, tuiles, meubles de bain etc.",
          image: "",
          site: "https://www.rassoulbuilding.com/"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Senegal Bois",
          profil: "Menuiserie ébéniste industrielle: fabrication, réparation, rénovation ou entretien de tout élément bois.",
          image: "",
          site: "https://senegal-bois.com/"
        },

        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "SETIM AFRIQUE",
          profil: "Spécialisée depuis 1993 dans l’étanchéité des bâtiments afin de répondre aux besoins spécifiques, d’isolation et d’imperméabilisation, des professionnels et particuliers.",
          image: "",
          site: "http://setim-afrique.com/-Etancheite-Liquide-"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Sika Sénégal",
          profil: "Sika Sénégal est la dernière filiale du groupe Sika spécialisée dans la production d’adjuvants liquide et poudre, le reconditionnement de cartouches de silicone, la production de mortier et la production de la colle à carrelage. Sika Sénégal dessert le Sénégal ainsi que ses sous régions mais également le Mali, la Gambie et la Guinée Conakry avec son canal de distributions et ses ventes directes.",
          image: "",
          site: "https://sen.sika.com/fr/construction/cuvelages-impermeabilisations.html"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "SMT Sénégal",
          profil: "Fournisseur de matériels BTP, manutention, recyclage et transport.",
          image: "",
          site: "https://www.smt.network"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Sociétè Dakaroise de Construction Métallique (Sodacom)",
          profil: "Domaines des menuiseries Aluminium-Bois et Métallique, création d'une fabrique de Meubles de Cuisines-Dressings-Salles de Bain-Aménagements Intérieurs sous le Label Maison & Espace.",
          image: "",
          site: "https://www.maison-espace.com"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Sococim Industries",
          profil: "Industrie de ciment en Afrique de l'Ouest.",
          image: "",
          site: "https://www.sococim.com/"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "SOFAMAC",
          profil: "Société de fabrication de matériaux de construction. Les briques rouges, les tuiles et les carreaux en terre cuite sont depuis des millénaires des matériaux prisés pour leur grande qualité dans la construction.",
          image: "",
          site: "http://sofamac.sn/"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "SOKAMOUSSE",
          profil: "Production de Matelas Orthopédiques et Mousse, produits de literie et tapisserie.",
          image: "",
          site: "https://www.senegal-export.com/sokamousse.html"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Structures en Acier et Services (Sas Sénégal)",
          profil: "Spécialisée dans la conception, la réalisation et la distribution de construction en acier sur mesure, de haute qualité, mais aussi dans la transformation de l’acier. Elle développe un panel de services et de produits locaux et importés destinés au secteur du bâtiment, des travaux publics, de la construction et de l’industrie.",
          image: "",
          site: "https://www.linkedin.com/company/sas-senegal"
        },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Tôlerie Remorques Combedimanche (TRC)/Filiale du groupe français COMBEDIMANCHE SAS",
          profil: "Tôlerie Industrielle développant en plus de la sous-traitance, ses propres produits comme des remorques, des bennes, de la décoration métallique, du mobilier urbain ainsi que du négoce.",
          image: "",
          site: "https://www.trc.sn/"
        },
        {
          secteur: "Éducation",
          nom: "BEM",
          profil: "Bordeaux Management School Senegal propose des formations en Bachelor (BAC +3) et en Master.",
          image: "",
          site: "https://bem.sn/"
        },
        {
          secteur: "Éducation",
          nom: "Centre Coaching Incubation Farmata Mactar Ndiaye",
          profil: "Centre spécialisé dans le coaching et le management de demain.",
          image: "",
          site: "https://www.2cicoachingsenegal.com"
        },

        {
          secteur: "Éducation",
          nom: "Centre d’Etudes des Sciences et Techniques de l’Information (CESTI)",
          profil: "Centre de formation ayant pour mission de former des journalistes et techniciens en information capables d’opérer en Afrique et partout dans le monde, capables d’évoluer dans le monde de l’information et de la communication et d’en devenir des experts.",
          image: "",
          site: "https://cesti.ucad.sn/"
        },
        {
          secteur: "Éducation",
          nom: "Centre Régional de Leadership Yali Afrique de l'Ouest",
          profil: "projet de l'agence américaine ciblant les jeunes entre 18 et 35 ans ayant un potentel de leadership et proposant aux futurs leaders de 25 pays africains des compétences, des outils, des opportunités leur permettant de réaliser leur rêve, et ainsi façonner l’avenir du continent.",
          image: "",
          site: "https://www.yaliafriquedelouest.org"
        },
        {
          secteur: "Éducation",
          nom: "Centre Trainmar de Dakar Université Maritime et Logistique",
          profil: "Centre de formation continue spécialisé dans le domaine des transports maritimes et des ports.",
          image: "",
          site: "https://www.trainamar.sn"
        },
        {
          secteur: "Éducation",
          nom: "ESUP Dakar",
          profil: "Depuis sa création dans les années 2000 au Sénégal, l’ESUP de Dakar a déjà formé plus de 20 000 cadres.",
          image: "",
          site: "http://esupdakar.sn"
        },
        {
          secteur: "Éducation",
          nom: "INPG SENEGAL",
          profil: "Ecole de formation en pétrole et gaz.",
          image: "",
          site: "https://www.inpg.sn/"
        },
        {
          secteur: "Éducation",
          nom: "Institut d’Etudes et d’Evaluations des Politiques Publiques et Stratégies (I2EPS)",
          profil: "Formation ( longue et courte durée), Recherche-publication, Evaluation des Politiques publiques, Stratégies et Cabinet de  Consultance juridique aux Etats et aux Entreprises.",
          image: "",
          site: "https://www.i2eps.com"
        },
        {
          secteur: "Éducation",
          nom: "Institut Supérieur de Management (ISM)",
          profil: "L’établissement a noué également de nombreux partenariats avec des universités internationales.",
          image: "",
          site: "https://www.groupeism.sn/"
        },
        {
          secteur: "Éducation",
          nom: "Institut Technique de Commerce ITECOM",
          profil: " ITECOM de Dakar offre des formations allant de la Licence Professionnelle (en management de commerce international par exemple), au Master 1 et 2.",
          image: "",
          site: "https://www.campus-teranga.com/etablissement-196/institut-technique-de-commerce"
        },
        {
          secteur: "Éducation",
          nom: "ISCOM Sup’ Management Dakar",
          profil: "L’institut supérieur de commerce et management propose des formations allant du cycle de Licence à celui du Master 1 et 2.",
          image: "",
          site: "https://iscom.sn"
        },
        {
          secteur: "Éducation",
          nom: "Université Amadou Makhtar Mbow de Dakar",
          profil: "Université.",
          image: "",
          site: "https://uam.sn/"
        },
        {
          secteur: "Éducation",
          nom: "Université Cheikh Anta Diop de Dakar",
          profil: "Université.",
          image: "",
          site: "https://www.ucad.sn/"
        },
        {
          secteur: "Éducation",
          nom: "Université euro Afrique UEA",
          profil: "Les formations proposées par l’établissement vont du cycle de Licence à celui du Master.",
          image: "",
          site: "https://universiteeuroafrique.com/fr/"
        },
        {
          secteur: "Éducation",
          nom: "Université Gaston Berger de Saint-Louis",
          profil: "Université.",
          image: "",
          site: "https://www.ugb.sn/"
        },
        {
          secteur: "Éducation",
          nom: "Université Iba Der Thiam de Thiès",
          profil: "Université.",
          image: "",
          site: "https://www.univ-thies.sn/"
        },
        {
          secteur: "Éducation",
          nom: "UVS",
          profil: "L’Université virtuelle du Sénégal.",
          image: "",
          site: "https://www.uvs.sn/"
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "AB Business Sénégal",
          profil: "Fournisseur de fourniture de matériel médical à domicile œuvrant au Sénégal et livrant sur tout le pays.",
          image: "",
          site: "https://abbusiness-sn.com/"
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "Afrique Conception et Distribution (ACD)",
          profil: "Fournisseur de services spécialisés dans le domaine médico-chirurgical avec la commercialisation de matériels médicaux, de mobiliers hospitaliers et instrumentations, de matériels de salle d’opération, d’appareils respiratoires, électro et autres.",
          image: "",
          site: "https://acd.sn/"
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "Air Liquide Sénégal",
          profil: "Entreprise offrant du gaz, des équipements et des services à ses clients dans tout le pays.",
          image: "",
          site: "https://www.airliquide.com/fr/groupe/senegal"
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "B2AD Médical",
          profil: "Fournisseur en matériel médical pour les professionnels de santé.",
          image: "",
          site: "https://b2admedical.com/"
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "Biopro Solutions",
          profil: "Entreprise de conseil, de distribution et de maintenance de matériel médical et scientifique.",
          image: "",
          site: "http://biopro.sn/"
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "Chimtec",
          profil: "Produits chimiqques, Marquage industriel et produits d'imprimerie, présent au Sénégal, en Côte d'Ivoire, au Ghana, au Mali et au Cameroun.",
          image: "",
          site: "https://www.chimtec.org/"
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "Dynapharm Internationale",
          profil: "Société qui importe et distribue principalement des compléments alimentaires, des engrais végétaux, des produits pharmaceutiques génériques, des produits de toilette traditionnels à base de plantes, des produits de toilette cosmétiques et des produits de beauté dans le monde entier via Multi- niveau/Marketing de réseau.",
          image: "",
          site: "https://dynapharm.net/ph/"
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "Industries Chimiques du Sénégal(ICS)",
          profil: "Société du groupe Indorama Corporation est le plus grand complexe industriel du Sénégal et le plus grand producteur de produits d'engrais phosphatés en Afrique subsaharienne.",
          image: "",
          site: "https://www.ics.sn/"
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "Laborex Sénégal",
          profil: "1er grossiste répartiteur au Sénégal, leader dans la distribution de médicaments et produits parapharmaceutiques pour les pharmacies et les établissements agrées sur le territoire.",
          image: "",
          site: "https://www.laborex-senegal.com/fr/"
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "Philip Morris",
          profil: "Fabrication de produits du tabac chauffés et de cigarettes.",
          image: "",
          site: "https://www.pmi.com/"
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "Ricardo Molina West Africa",
          profil: "Une des principales entreprises responsables de la distribution de produits chimiques et d'ingrédients naturels de spécialité et présente sur 16 secteurs industriels des produits agricoles, cosmétiques et alimentions, produits de détergence etc.",
          image: "",
          site: "https://ricardomolina.com/"
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "RMG Sénégal/Ex Polychimie",
          profil: "Distribution de spécialités agrochimiques, production agricole commerciale et familiale, transformation et commercialisation des produits d’agriculture et traitement des déchets liés à l’activité agricole, présent en Afrique de l'Ouest et Centrale.",
          image: "",
          site: "https://www.rmgconcept.com"
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "Sanofi Afrique de l'Ouest",
          profil: "Entreprise mondiale de soins de santé innovante fournissant des traitements potentiellement révolutionnaires et la protection de vaccins vitaux à des millions de personnes, ainsi qu'un accès abordable à nos médicaments dans certains des pays les plus pauvres du monde.",
          image: "",
          site: "https://www.sanofi.com/"
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "Valdafrique Laboratoires canonne",
          profil: "un des acteurs majeurs du marché des produits d’hygiène et de santé en Afrique de l’ouest. Grâce à son statut de laboratoire pharmaceutique, la société a toujours misà à la disposition des populations des produits pharmaceutiques et para-pharmaceutiques de qualité à des prix accessibles.",
          image: "",
          site: "http://www.valdafrique.com/"
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "Adama Paris",
          profil: "Fashion designer.",
          image: "",
          site: "https://adamaparis.com/index.php/fr/"
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "Afro & Nature",
          profil: "Distribtion et transformation des produits de soins corporels et capillaires naturels.",
          image: "2602bf_1be9bc3051df40f78e6c7baf4b9fa4b5_mv2",
          site: "https://www.afronaturel.com/"
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "B MESURE",
          profil: "Maison de haute couture spécialiste de la couture sur mesure.",
          image: "2602bf_1be9bc3051df40f78e6c7baf4b9fa4b5_mv2",
          site: "http://www.bmesure.net/"
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "COTOA",
          profil: "Confection textile et bâches.",
          image: "cotoa1938",
          site: "https://www.cotoa.sn/"
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "Diarra Blu",
          profil: "Contemporary lifestyle brand.",
          image: "DIARRABLU-logo_140x@2x",
          site: "https://diarrablu.com/"
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "Francesca Maroquinerie de luxe",
          profil: "Maroquinerie de luxe : sacs, chaussures et accessoires en peau de crocodile, autruche ou iguane.",
          image: "7fa598fe0664988c2530a11a6389db",
          site: "https://www.au-senegal.com/francesca,3124.html?lang=fr"
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "Gandour",
          profil: "Parfumerie, Fabrique de Produits Cosmétiques.",
          image: "npgsenegal",
          site: "https://www.npgsenegal.com/"
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "Jolof Cuir Collection",
          profil: "Marque Sénégalaise de Maroquinerie proposant des produits originaux et authentiques fabriqués avec du cuir 100% sénégalais et vendus à un prix accessible.",
          image: "Logo-JCC-2-1",
          site: "https://jolofcuircollection.com/"
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "Khady Racine (KR)",
          profil: "Mode.",
          image: "1623159795224",
          site: "https://www.linkedin.com/in/khady-racine-160402163/"
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "Modesénégal",
          profil: "Portail d'accès au secteur de la mode au Sénégal.",
          image: "mosen",
          site: "https://www.modesenegal.com/"
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "Quartier Sandaga",
          profil: "Marque ayant pour mission la mise en avant du savoir faire africain et promouvoir les expressions africaines sur des vêtements de qualité.",
          image: "quartiersandaga",
          site: "https://www.quartiersandaga.com/"
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "Tongoro",
          profil: "Fashion 100% made in Africa.",
          image: "tongoromode",
          site: "https://www.tongoro.com/"
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "WELLNESS",
          profil: "Produits de cosmétique bio et naturel.",
          image: "wellness",
          site: "https://senegal-export.com/wellness.html"
        },
        {
          secteur: "Services financiers",
          nom: "Allianz Sénégal Assurances",
          profil: "Compagnie d'assurance.",
          image: "alianz",
          site: "https://www.allianz.sn/"
        },
        {
          secteur: "Services financiers",
          nom: "Amsa Assurances",
          profil: "Compagnie d'assurance.",
          image: "img_apropos-1024x900-Recupere",
          site: "https://www.amsaassurances.com"
        },
        {
          secteur: "Services financiers",
          nom: "Ascoma Sénégal",
          profil: "Conseil et courtier en Assurances.",
          image: "acomaassurance",
          site: "https://www.ascoma.com/"
        },
        {
          secteur: "Services financiers",
          nom: "Askia Assurance",
          profil: "Compagnie d'assurance.",
          image: "askia",
          site: "https://www.askiaassurances.net/"
        },
        {
          secteur: "Services financiers",
          nom: "Axa Assurance",
          profil: "Compagnie d'assurance.",
          image: "logo_axa_fr_FR",
          site: "https://www.axa.sn/"
        },
        {
          secteur: "Services financiers",
          nom: "Bank of Africa (BOA)",
          profil: "Banque présente dans implantée dans 17 pays.",
          image: "Logo_PP_Positif-small",
          site: "https://www.boasenegal.com/"
        },
        {
          secteur: "Services financiers",
          nom: "Banque Agricole",
          profil: "Banque commerciale distribuant du crédit de façon à promouvoir les activités économiques en milieu rural, urbain et périurbain.",
          image: "logo_cncas",
          site: "https://www.labanqueagricole.sn/accueil"
        },
        {
          secteur: "Services financiers",
          nom: "Banque Atlantique",
          profil: "Banque présente dans les  huit (8) Etats membres de l’Union Monétaire Ouest Africaine (UMOA) Bénin, Burkina, Côte d’Ivoire, Guinée-Bissau, Mali, Niger, Sénégal et Togo.",
          image: "BACI-Logo-slogan",
          site: "https://www.banqueatlantique.net/"
        },
        {
          secteur: "Services financiers",
          nom: "Banque Centrale des Etats d’Afrique de l’Ouest (BCEAO)",
          profil: "Institut d’émission commun aux huit (8) Etats membres de l’Union Monétaire Ouest Africaine (UMOA) Bénin, Burkina, Côte d’Ivoire, Guinée-Bissau, Mali, Niger, Sénégal et Togo.",
          image: "logo_bcao_fr",
          site: "https://www.bceao.int/"
        },
        {
          secteur: "Services financiers",
          nom: "Banque de l’Habitat du Sénégal (BHS)",
          profil: "Banque avec comme domaine d’activité principal le financement de l’immobilier, en accession à la propriété, avec une priorité pour le logement social.",
          image: "logo_bhs_0",
          site: "https://www.bhs.sn/"
        },
        {
          secteur: "Services financiers",
          nom: "Banque Islamique du Sénégal (BIS)",
          profil: "Etablissement financier ayant pour objet social directement ou indirectement toutes opérations de banque, de finance et de crédit, au moyen de fonds reçus de personnes privées ou publiques, l'octroi de crédit à court, moyen et long terme, toutes opérations financières Islamiques selon les principes de l’Islam.",
          image: "Logo-bis",
          site: "https://bis-bank.com/"
        },
        {
          secteur: "Services financiers",
          nom: "Banque Nationale pour le Développement Economique (BNDE)",
          profil: "Banque à vocation universelle spécialisée dans le financement des PME-PMI avec un modèle de partenariat Public-Privé.",
          image: "logobnde",
          site: "https://www.bnde.sn/"
        },
        {
          secteur: "Services financiers",
          nom: "Banque Sahélo-Saharienne pour l’Investissement et le Commerce (BSIC)",
          profil: "Banque ayant pour mission la collecte des ressources financières publiques et privées afin de les utiliser pour contribuer au financement du développement économique et social, et du commerce extérieur dans l’espace sahélo-saharien.",
          image: "logo_bsic-21",
          site: "https://bsicbank.com/senegal/"
        },
        {
          secteur: "Services financiers",
          nom: "BGFI Bank Sénégal",
          profil: "Banque présente dans 11 pays et leader en zone CEMAC (Communauté Economique et Monétaire de l’Afrique Centrale).",
          image: "logo-e1470418907567",
          site: "https://senegal.groupebgfibank.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "AQUATECH SENEGAL",
          profil: "45 ans d’expérience dans la gestion et la distribution de l’eau, présent dans 24 pays dans le monde dont 5 en Afrique. Elle est l’instrument d’application de la réforme de l’hydraulique au Sénégal.",
          image: "cropped-AQ-version-horizontale-1",
          site: "https://aquatech.sn/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Alpha Engineering Group (ALPHEG)",
          profil: "Ingénieur électricien.",
          image: "",
          site: "https://alpheg.business.site/?utm_source=gmb&utm_medium=referral"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Atlantic Petroleum Africa (APA)",
          profil: "Distribution et importation de produits hydrocarbures raffinés.",
          image: "LOGO-APA2-1536x935",
          site: "https://atlanticpetroleumafrica.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "BEIN2E",
          profil: "Bureau d'etude - ingénieur electricien.",
          image: "logo-bnd",
          site: "https://www.linkedin.com/pulse/bein2e-sas-projet-detude-et-de-realisation-20-pour-un-ndiaye/?trk=articles_directory&originalSubdomain=de"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "BP Senegal Investments Limited",
          profil: "Entreprise énergétique intégrée avec des opérations en Europe, en Amérique du Nord et du Sud, en Australasie, en Asie et en Afrique Fournissant des solutions énergétiques à des clients du monde entier.",
          image: "logobp",
          site: "https://www.bp.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Bet plus sa",
          profil: "Geotechnique- geomatique - electricité et eau.",
          image: "logo-bet",
          site: "https://betplus-sn.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "CB MOTORS",
          profil: "Distribution de lubrifiants pour véhicules.",
          image: "logo-champion",
          site: "https://www.championlubes.com/en-us"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Cogelec energy",
          profil: "Ingénieur électricien.",
          image: "logo-cogelec",
          site: "https://cogelecsn.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Dakarelec",
          profil: "Installation électrique de tous bâtiments et raccordement au réseau de distribution, Eclairage intérieur et extérieur, Eclairage de secours…",
          image: "logo-dakar-elec",
          site: "https://cogelecsn.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Elton Oil Company",
          profil: "Distribution de carburant et des services auto.",
          image: "elton-logo",
          site: "https://www.eltonoil.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Engineering & Environment Services (Cabinet EES)",
          profil: "Consultant en environnement.",
          image: "logo-ees",
          site: "https://www.cabinet-ees.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Environnement, déchets, eaux (EDE)",
          profil: "Société d’ingénierie, conseils contribuant au développement du secteur de l’assainissement et de l’eau, présent au Sénégal, au Burkina Faso, au Niger, en Côte d'Ivoire et en Haiti.",
          image: "logo-ede",
          site: "https://www.cabinetede.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Equip Plus",
          profil: "Spécialiste dans la mise en oeuvre des solutions électro-hydro-mécaniques.",
          image: "logo-equip",
          site: "https://www.equiplus.sn/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "GAUFF GmbH & Co. Engineering KG",
          profil: "Entreprise familiale encourageant l’amélioration des conditions économiques et socio-économiques grâce au développement, à la planification et à la mise en œuvre d’infrastructures essentielles sur le continent africain, mais aussi dans notre patrie, l’Allemagne et le monde entier.",
          image: "logo-gauff",
          site: "https://www.gauff.net/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Grande Côte Opérations SA/filiale Groupe Eramet",
          profil: "Exploitation de sables minéralisés et production de l’ilménite et du zircon.",
          image: "logo-eramet",
          site: "https://www.eramet.com/en/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Groupe Soterco",
          profil: "Consultant en ingénierie.",
          image: "logo_soterco",
          site: "https://www.groupesoterco.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "IBRIZ",
          profil: "Société de technologie solaire axée sur l’utilisation productive de l’énergie solaire dans l’agriculture.",
          image: "Attachment_1621121723",
          site: "https://ibriz.co/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "IDC – International Drilling Company",
          profil: "Société de forage fournissant des solutions modernes à l’industrie minière mondiale.",
          image: "logo-idc",
          site: "https://www.idc-drilling.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "LSE- group vinci",
          profil: "Energie.",
          image: "logo-lse",
          site: "https://www.lse-energies.com/sn/QUE+FAISONS+NOUS"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Lub & Supply",
          profil: "Lubrification, Maintenance et Fournitures industrielles.",
          image: "logo-lub",
          site: "https://www.linkedin.com/company/lub-supply/?originalSubdomain=sn"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Matrix senegal",
          profil: "Management de projets, AMO, étude, conception. Calculs (réseaux de fluides – tuyauterie/piping), charpente métallique. Électricité, automatisme, instrumentation : audit et expertise. Marchés publics : APS, APD/PC, PRO , DCE. HVAC (CVC ), HSE, maintenance et fiabilisation.",
          image: "logo-matrix",
          site: "https://matrixsenegal.com/ingenierie-des-installations-generales/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Mineex",
          profil: "Forage et Minage.",
          image: "logo-epc",
          site: "https://www.epc-mineex.sn/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Oryx Sénégal SA",
          profil: "Fournisseur indépendants de produits et services pétroliers et gaziers les plus importants et les plus anciens en Afrique subsaharienne.",
          image: "logo-oryx",
          site: "https://www.oryxenergies.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "PMI AFRIQUE",
          profil: "Spécialisé dans la conception et la réalisation d’installations de traitement d’eau en Afrique de l’Ouest, partenariat exclusif avec le leader européen du secteur, BWT.",
          image: "logo-pmi",
          site: "https://pmi-afrique.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "SC Afrique SARL",
          profil: "Ingénieurs_ conseils.",
          image: "logo-sc",
          site: "https://scafrique.com/en/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "SEN BIO PLASTICS",
          profil: "Recyclage de déchets plastiques, négoce de matières premières plastiques et de produits chimiques de laboratoires.",
          image: "logo-sen-bio",
          site: "https://www.linkedin.com/company/senbioplastics-sas/about/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "SEN'EAU",
          profil: "Entreprise en charge de l’exploitation et de la distribution de l’eau potable en zone urbaine et péri-urbaine du Sénégal.",
          image: "logo-sen-eau",
          site: "https://www.seneau.sn/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "SEPHOS",
          profil: "Production de roche phosporique.",
          image: "",
          site: "https://sephossenegal.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "SGF",
          profil: "Distribution d'hydrocarbures et de lubrifiants.",
          image: "Logo-SGF-Vrai",
          site: "https://sgf.sn/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Sahel Gaz",
          profil: "Production et de fourniture d'énergies : pétrole et biocarburants, gaz naturel et gaz verts, renouvelables et électricité.",
          image: "logo-blanc-png",
          site: "https://sahelgaz.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Serex sarl",
          profil: "Société d'étude, de réalisation et d'exploitation de l'énergie.",
          image: "logo-serex",
          site: "https://serex.sn/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Siat senegal",
          profil: "SIAT SÉNÉGAL est une société d’ingénierie ayant pour mission d’apporter son expertise dans toutes les phases de réalisation d’un projet de la formulation au suivi-évaluation en passant par le suivi et le contrôle de son exécution. Elle s’est fixée comme objectif d’assurer des prestations de qualité en matière d’études, de conseils et d’assistance technique.",
          image: "logo-siat",
          site: "https://siat-senegal.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Sociétè Italo-Sénégalaise pour le Développement des Energies Alternatives au Sénégal (SISDEA)",
          profil: "Energies renouvelables.",
          image: "",
          site: ""
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Société Africaine de raffinage (SAR)",
          profil: "Société ayant pour vocation le raffinage du pétrole brut pour l’approvisionnement du marché sénégalais en produits pétroliers.",
          image: "logo-sar2",
          site: "http://www.sar.sn/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Torex Sarl",
          profil: "Conception et réalisation des stations de pompage d’eau dans le domaine rural et urbain, Equipements hydrauliques, Equipements électriques, automatismes, automates programmables, Télétransmission : supervision, télégestion et télésurveillance.",
          image: "400pngdpilogocropped",
          site: "http://torexsn.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Total Energies",
          profil: "automates programmables, Télétransmission : supervision, télégestion et télésurveillance.",
          image: "logo-total",
          site: "https://totalenergies.sn/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Trouvay & Cauvin",
          profil: "Fournisseur de solutions de tuyauterie au secteur de l’énergie.",
          image: "TC-GROUP-LOGO-1-1536x696",
          site: "https://trouvaycauvin.com/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Tsg sénégal-Cosetam",
          profil: "Fournisseur mondial d’équipements et de services pour les stations-service et les sociétés pétrolières.",
          image: "logo-tsg",
          site: "https://www.tsg-solutions.com/sn/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Unité de Coordination de la Gestion des Déchets solides (UCG)",
          profil: "Agence rattachée au Ministère de l'Urbanisme, du Logement et de l'Hygiène publique en chargé d’accompagner les collectivités locales dans la prise en charge de leurs compétences, en matière de gestion des déchets solides.",
          image: "logo_UCG",
          site: "https://www.ucg.gouv.sn/"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Vinci energies senegal",
          profil: "Actif dans le secteur des concessions, de l’énergie et de la construction, présent dans plus de 120 pays. Son ambition, face à l’urgence environnementale, est d’accélérer la transformation du cadre de vie, des infrastructures et de la mobilité.",
          image: "logo-vinci",
          site: "https://www.vinci.com/vinci.nsf/fr/index.htm"
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "VVivo Energy Sénégal",
          profil: "Distribution et commercialisation des carburants et lubrifiants de la marque Shell et Engen, présent dans 23 pays en Afrique.",
          image: "vivo-logo_0",
          site: "https://www.vivoenergy.com/fr"
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "Association Nationale des Bijoutiers du Sénégal (ANBS)",
          profil: "Etude et défense des interets des membres et de la profession.",
          image: "logo-anbs",
          site: "https://www.facebook.com/associationnationale?mibextid=ZbWKwL"
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "Association des exploitants semi-mécanisée d'or et de substances connexes du Sénégal",
          profil: "Etude et défense des interets des membres et de la profession.",
          image: "logo-anbs",
          site: "https://www.facebook.com/associationnationale?mibextid=ZbWKwL"
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "CIS Club des investisseurs du Sénégal",
          profil: "Club des investisseurs du Sénégal.",
          image: "logo-cis",
          site: "https://clubdesinvestisseurs.org/index.php/accueil-english/"
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "CNES",
          profil: "Confédération National des Employeurs du Sénégal.",
          image: "logo-cnes",
          site: "https://cnes.sn/"
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "CNP Conseil National du Patronat du Sénégal",
          profil: "Conseil National du Patronat du Sénégal (CNP).",
          image: "logo-1553107208",
          site: "https://www.cnp.sn/"
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "Chambre de Commerce d'Industrie et d'Agriculture de dakar (CCIAD)",
          profil: "Représentant de l’ensemble des opérateurs économiques et défenseur des intérêts généraux des entreprises industrielles, commerciales et agricoles.",
          image: "logo-cciad",
          site: "https://cciad.sn/"
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "Confédération des Syndicats Autonomes (CSA Sénégal-)",
          profil: "Syndicat des travailleurs.",
          image: "logo-csa",
          site: "https://www.facebook.com/confederationcsa?mibextid=ZbWKwL"
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "Institut De Technologie Alimentaire (ITA)",
          profil: "Institut de recherche-développement à voccation agroalimentaire.",
          image: "itaPlan-de-travail-1",
          site: "https://ita.sn/"
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "Institut Sénégalais de Recherches Agricoles (ISRA)",
          profil: "Recherches dans les domaines de production animales, végétales, forestières, halieutiques et socio-économiques.",
          image: "logo-isra",
          site: "https://isra.sn/"
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "MEDS",
          profil: "Mouvement des entreprises du Sénégal.",
          image: "logo-meds",
          site: "https://meds-senegal.com/"
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "UNCCIAS",
          profil: "Union des chambres de commerce.",
          image: "logo-uncias",
          site: "https://www.facebook.com/unccias"
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "WIM Sénégal",
          profil: "Promotion du leadership féminin dans le secteur féminin.",
          image: "logo-wim",
          site: "https://wimsenegal.org/"
        },
        {
          secteur: "Machines et Materiels",
          nom: "Al Yosra International Company (AIC)",
          profil: "Société de la famille FAKHFAKH du développement des solutions industriel & Ingénierie - Conseil & Main-d’œuvre et délégation des équipements et des produits industriels.",
          image: "logo-aic",
          site: "https://www.alyosra-ic.com/fr/"
        },
        {
          secteur: "Machines et Materiels",
          nom: "BIAGROUP",
          profil: "Distribution de matériels et équipements industriels.",
          image: "logo-bia",
          site: "https://biagroup.com/group/en"
        },
        {
          secteur: "Machines et Materiels",
          nom: "Bepco Sénégal",
          profil: "Fournisseur mondial de pièces pour tracteurs et matériels agricoles.",
          image: "logo-bepco",
          site: "https://www.bepcoparts.com/fr-xx"
        },
        {
          secteur: "Machines et Materiels",
          nom: "Bernabé Sénégal",
          profil: "Spécialisée dans la vente en détail et la distribution d'équipements industriels et du matériel en acier.",
          image: "logo-bernabe",
          site: "https://yeshigroup.com/yeshigroup.com/fr/groupe.html"
        },
        {
          secteur: "Machines et Materiels",
          nom: "COGEKO DRILL WP",
          profil: "Fournisseur d'équipements de forage, de tuyauterie et autres matériels de plomberie.",
          image: "logo-bernabe",
          site: "https://cogekodrill.com/"
        },
        {
          secteur: "Machines et Materiels",
          nom: "Cummings Afrique de l'Ouest",
          profil: "Spécialiste dans la fabrication et la distribution de groupe électrogène.",
          image: "logo-cummings",
          site: "https://www.cummins.com/"
        },
        {
          secteur: "Machines et Materiels",
          nom: "Digital Electronic Sarl",
          profil: "Fournisseur de matériels industriels spécialisés dans le domaine de l'automatisme, de l'électricité et du convoyage. Nous représentons officiellement au Sénégal les marques FESTO, IFM et BENNE SA.",
          image: "logo-de",
          site: "https://www.digitalelectronicsn.com/"
        },
        {
          secteur: "Machines et Materiels",
          nom: "Friedlander",
          profil: "Fournisseur de solutions en ingénierie, travaux neufs et maintenance industrielle.",
          image: "logo-ortec-group-2018",
          site: "https://friedlander-ortec.com/"
        },
        {
          secteur: "Machines et Materiels",
          nom: "SAEZ CONSULTING SENEGAL",
          profil: "Cabinet de conseil en industries et construction.",
          image: "logo-saez",
          site: "https://saez-it.com/"
        },
        {
          secteur: "Machines et Materiels",
          nom: "SMR Dubé",
          profil: "Réparation et maintenance industrielle: transformateurs, moteurs électriques et locomotives.",
          image: "SMR-DUBE-LOGO_web",
          site: "https://smrdube.com/"
        },
        {
          secteur: "Machines et Materiels",
          nom: "Scomath SA",
          profil: "Mécanique générale et industrielle, fabrication, vente, location et réparation de matériel industriel, moteurs et équipements professionnels.",
          image: "NOUVEAU-LOGO-SCOMATH-transparent-min",
          site: "https://scomath.com/"
        },
        {
          secteur: "Machines et Materiels",
          nom: "Senegal Automation Technology Assistance",
          profil: "Automatisme industriel,Instrumentation et Electricité industrielle.",
          image: "logo-sata",
          site: "http://senegalautomation.com/"
        },
        {
          secteur: "Machines et Materiels",
          nom: "Sonerco/Filiale du Groupe Cosemad",
          profil: "Spécialisée dans l’énergie, l’industrie, le BTP, l’hydraulique, et les équipements techniques.",
          image: "logo-cosemad-site",
          site: "https://cosemad.sn/sonerco/"
        },

      ],
    };
  },
  computed: {
    filteredUser() {
      const query = this.searchQuery.toLowerCase();
      if (this.searchQuery === "") {
        return this.secteur;
      }
      return this.secteur.filter((user) => {
        return user.toLowerCase().includes(query);
      });
    },
    setSearchSector() {
      return this.listentreprise
        .filter((sector) => !sector.secteur.indexOf(this.searchSector))
        .filter((sector) => !sector.nom.toLowerCase().indexOf(this.filter) || !sector.nom.toUpperCase().indexOf(this.filter))
        .sort((a, b) => {
          if (a.nom < b.nom) {
            return -1;
          } else {
            return 1;
          }
        })
        .filter((row, index) => {
          let start = (this.currentPage - 1) * this.pageSize;
          let end = this.currentPage * this.pageSize;
          if (index >= start && index < end) return true;
        })
        .sort((a, b) => {
          let modifier = 1;
          if (this.currentSortDir === "desc") modifier = -1;
          if (a[this.currentSort] < b[this.currentSort]) return -1 * modifier;
          if (a[this.currentSort] > b[this.currentSort]) return 1 * modifier;
          return 0;
        })

    },
    //   filterByCategory: function () {

    // }
  },
  methods: {
    nextPage() {
      console.log("next");
      if (this.currentPage * this.pageSize < this.listentreprise.length) {
        this.currentPage++;
      }
    },
    prevPage() {
      console.log("prev");
      if (this.currentPage > 1) {
        this.currentPage--;
      }
    },

    sort(s) {
      //if s == current sort, reverse
      if (s === this.currentSort) {
        this.currentSortDir = this.currentSortDir === "asc" ? "desc" : "asc";
      }
      this.currentSort = s;
    },

    showInscription() {
      this.$router.push("/inscription");
    },
    setSearchQuery(data) {
      this.searchQuery = data;
    },
    changeActive(e) {
      e.target.classList.toggle("checked");
    },
    changeColor(e) {
      e.target.classList.add("red");
    },
    showMission() {
      this.$router.push("/mission-economique-belge-au-senegal");
    },
    listAgro() {
      if (
        this.searchQuery ===
        "Agriculture / Agroalimentaire / Aliments / Boissons"
      ) {
        this.$router.push(
          "/list-entreprise-secteur-agriculture-agroalimentaire-aliment-boisson"
        );
      }
      // if (this.searchQuery === "Chaux") {
      //   this.$router.push("/list-entreprise-secteur-chaux");
      // }
      if (this.searchQuery === "ICT et électronique") {
        this.$router.push("/list-entreprise-secteur-tic-audiovisuel");
      }
      if (this.searchQuery === "Transport et logistique") {
        this.$router.push("/list-entreprise-secteur-transport-et-logistique");
      }
      if (this.searchQuery === "Services / Consultance") {
        this.$router.push("/list-entreprise-secteur-service-consultance");
      }
      if (
        this.searchQuery ===
        "Construction services / Infrastructure / Ingénieurie"
      ) {
        this.$router.push("/list-contruction-infrastructure-ingenierie");
      }

      // if (this.searchQuery === "Decoration") {
      //   this.$router.push("/list-contruction-infrastructure");
      // }
      if (
        this.searchQuery ===
        "Matériaux construction / Machines / Véhicules / Equipements / Outillage"
      ) {
        this.$router.push("/list-entreprise-machine-equipement-materiaux");
      }
      if (this.searchQuery === "Metallurgie") {
        this.$router.push("/list-entreprise-steel");
      }
      if (this.searchQuery === "Médical / Pharmaceutique / Chimie") {
        this.$router.push(
          "/list-entreprise-secteur-chimie-pharmaceutique-science-medical"
        );
      }

      if (this.searchQuery === "Electricite") {
        this.$router.push("/list-entreprise-secteur-electricite");
        console.log(this.secteur[1]);
      }
      if (
        this.searchQuery ===
        "Énergie / Eau / Environement / Technologies propres"
      ) {
        this.$router.push(
          "/list-entreprise-secteur-energie-environement-technologiepropre"
        );
      }
      if (
        this.searchQuery ===
        "Industries culturelles et créatives / loisirs / Tourisme"
      ) {
        this.$router.push(
          "/list-entreprise-secteur-tourisme-loisir-creative-culturelle"
        );
      }
      if (this.searchQuery === "Education") {
        this.$router.push("/list-entreprise-secteur-education");
      }
      if (this.searchQuery === "Luxe / Textile / Mode / Bien-être") {
        this.$router.push("/list-entreprise-secteur-modes-lifestyle-luxe");
      }
      if (this.searchQuery === "Services financiers") {
        this.$router.push("/list-entreprise-secteur-finance");
      }
      // if (this.searchQuery === "Energie /Environement / Technologie propre") {
      //   this.$router.push("/list-entreprise-secteur");
      // }

      // console.log(this.secteur[0]);
    },
  },

};
</script>
<style>
.cadre {
  border-radius: 0px 20px 0 20px;
  animation: appear 0.5s ease-in-out forwards;
}

.carde input[type="radio"] {
  /* Hide radio buttonns */
  opacity: 0;

  -webkit-appearance: none;
  appearance: none;
  position: absolute;

  margin: 10px;
  cursor: pointer;
}

.checked {
  background: green;
  color: #fff;
}

/* .checked::before {
    content: "✔";
    background-color: ;
  } */
.red {
  border-bottom: red 2px solid;
}
</style>