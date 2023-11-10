<template>
  <div class="bg-base-100">
    <HelloWorld />
    <ImageSenegal />
  </div>
  <!-- -------------------------bankrub--------------------------------- -->
  <div class="bg-base-100">
    <nav class="flex mb-4 px-6 py-6" aria-label="Breadcrumb">
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
              Belges intéressées par le Sénégal</a>
          </div>
        </li>
        <li  v-if="searchSector != ''">
          <div class="flex items-center">
            <svg class="w-6 h-6 text-gray-400" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd"
                d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z"
                clip-rule="evenodd"></path>
            </svg>
            <a href="#entreprise" 
              class="bg-gray-100 text-gray-800 text-xs font-medium mr-2 px-2.5 py-0.5 rounded-full dark:bg-gray-900 dark:text-gray-300">{{
                searchSector }}</a>
          </div>
        </li>

      </ol>
    </nav>

    <!-- <h5 id="mission"
      class="mb-2 text-2xl px-6 cursive uppercase font-semibold tracking-tight text-gray-900 dark:text-white">
      MISSION éCONOMIQUE BELGE AU sénégal / Dox ci yoonu koom belge fii ci
      sénégal -->
    <!-- <div class="w-full bg-white  bordered rounded-full h-2.5 dark:bg-gray-700">
            <div class="bg-red-600 h-1.5" style="width: 5%"></div>
          </div> -->
    <!-- </h5> -->
    <section class="bg-white dark:bg-gray-900">
      <div class="py-8 px-4 mx-auto max-w-screen-xl sm:py-16 lg:px-6">
        <div class="max-w-screen-xl p-10 text-left mb-8 lg:mb-16">
          <label id="entreprise"
            class="m-1 inline-flex carde items-center px-5 py-1 text-sm font-normal text-center text-gray-900  bg-gray-100 rounded-full  focus:ring-4 focus:outline-none active:ring-gray-300 dark:bg-gray-600 dark:hover:bg-gray-700 dark:focus:ring-gray-800">
            <input type="radio" v-model="searchSector" value="" />
            Sélectionner tout
            <!-- <span
              class="inline-flex justify-center items-center ml-2 w-4 h-4 text-xs font-semibold text-gay-900 bg-gray-400 rounded-full">
              171
            </span> -->
          </label>

          <label v-for="sect in this.secteur" :key="sect.nom"
            class="m-1 inline-flex carde items-center px-5 py-1 text-sm font-normal text-center text-gray-900 active:text-gray-900 bg-gray-100 rounded-full">
            <input type="radio" v-model="searchSector" :value="sect.nom" />
            {{ sect.nom }}
            <span
              class="inline-flex justify-center items-center ml-2 w-4 h-4 text-xs font-semibold text-gay-900 bg-gray-400 rounded-full">
              {{ sect.nombre }}
            </span>
          </label>
        </div>




        <div class=" col space-y-8 md:grid md:grid-cols-2 lg:grid-cols-3 md:gap-12 md:space-y-0">
          <div v-for="entreprise in setSearchSector" :key="entreprise.nom">

            <div
              class=" card h-100 p-6 bg-white border cadre border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700">
              <a :href="`${entreprise.site}`" target="_blank" title="Clique pour voir le site web">
                <div class="flex-shrink-0">
                  <span v-if="searchSector != ''"
                    class="bg-red-100 text-red-800 text-xs font-medium mr-2 px-2.5 py-0.5 rounded-full dark:bg-red-900 dark:text-red-300">{{
                      searchSector }}</span>
                  <img class="mb-4" :src="require(`@/assets/${entreprise.image}.png`)" :alt="entreprise.image" />

                  <h5 class="mb-2 text-xl uppercase cursive font-medium tracking-tight text-gray-900 dark:text-white">
                    {{ entreprise.nom }}
                  </h5>
                </div>
              </a>
              <p class="mb-3 font-normal text-gray-700 dark:text-gray-400 p-2">
                {{ entreprise.profil }}
              </p>
              <a :href="`${entreprise.site}`"
                class=" flex sm:w-auto bg-red-700 hover:bg-gray-700 focus:ring-4   focus:outline-none focus:ring-gray-300 text-white rounded-full inline-flex items-center justify-center px-4 py-2.5 dark:bg-gray-700 dark:hover:bg-gray-600 dark:focus:ring-gray-700">
                <!-- <svg class="mr-3 w-7 h-7" aria-hidden="true" focusable="false" data-prefix="fab" data-icon="apple" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 384 512"><path fill="currentColor" d="M318.7 268.7c-.2-36.7 16.4-64.4 50-84.8-18.8-26.9-47.2-41.7-84.7-44.6-35.5-2.8-74.3 20.7-88.5 20.7-15 0-49.4-19.7-76.4-19.7C63.3 141.2 4 184.8 4 273.5q0 39.3 14.4 81.2c12.8 36.7 59 126.7 107.2 125.2 25.2-.6 43-17.9 75.8-17.9 31.8 0 48.3 17.9 76.4 17.9 48.6-.7 90.4-82.5 102.6-119.3-65.2-30.7-61.7-90-61.7-91.9zm-56.6-164.2c27.3-32.4 24.8-61.9 24-72.5-24.1 1.4-52 16.4-67.9 34.9-17.5 19.8-27.8 44.3-25.6 71.9 26.1 2 49.9-11.4 69.5-34.3z"></path></svg> -->
                <div class="text-left ">
                  <!-- <div class="mb-1 text-xs">Download on the</div> -->
                  <div class="-mt-1 font-sans text-sm font-semibold flex ">
                    Consulter le site web
                    <svg class="w-5 h-5 ml-2" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                      <path
                        d="M11 3a1 1 0 100 2h2.586l-6.293 6.293a1 1 0 101.414 1.414L15 6.414V9a1 1 0 102 0V4a1 1 0 00-1-1h-5z">
                      </path>
                      <path d="M5 5a2 2 0 00-2 2v8a2 2 0 002 2h8a2 2 0 002-2v-3a1 1 0 10-2 0v3H5V7h3a1 1 0 000-2H5z">
                      </path>
                    </svg>
                  </div>
                </div>
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
  <Organisateur />
  <MyFooter />
</template>
<script>
import HelloWorld from './HelloWorld.vue';
import ImageSenegal from './ImageSenegal.vue';
import MyFooter from './MyFooter.vue';
import Organisateur from './Organisateur.vue';

export default {
  components: {
    ImageSenegal,
    HelloWorld,
    Organisateur,
    MyFooter
  },
  data() {
    return {
      searchQuery: "",
      searchSector: "",
      isVisible: false,
      showMenu: false,
      isLoading: true,
      secteur: [
        {
          nom: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nombre: 19,
        },
        {
          nom: "ICT et électronique",
          nombre: 11,
        },
        {
          nom: "Transport et logistique",
          nombre: 17,
        },
        {
          nom: "Services / Consultance",
          nombre: 20,
        },
        {
          nom: "Construction services / Infrastructure / Ingénierie",
          nombre: 12,
        },
        {
          nom: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nombre: 18,
        },
        // {
        //   nom: "Metallurgie",
        //   nombre: 3,
        // },
        {
          nom: "Médical / Pharmaceutique / Chimie",
          nombre: 10,
        },
        // {
        //   nom: "Électricité",
        //   nombre: 1,
        // },
        {
          nom: "Éducation",
          nombre: 20,
        },
        {
          nom: "Luxe / Textile / Mode / Bien-être",
          nombre: 7,
        },
        {
          nom: "Services financiers",
          nombre: 4,
        },
        {
          nom: "Énergie / Eau / Environement / Technologies propres",
          nombre: 13,
        },
        {
          nom: "Industries culturelles et créatives / loisirs / Tourisme",
          nombre: 8,
        },
        {
          nom: "Fédération et chambre de commerce",
          nombre: 10,
        },
        // {
        //   nom: "Enjeux Securitaire",
        //   nombre: 2,
        // },
      ],
      listentreprise: [
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "MEAM HOLDING",
          profil:
            "Chauffage, séchage, affinage et pasteurisation industriel par technologie mico-ondes.",
          image: "Logo-Image-Default",
          site: "https://meam-international.com/",
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "G-HITECH INDUSTRIES",
          profil:
            "G-Hitech Industries a mis au point des équipements capables d'exploiter avec efficacité l'énergie solaire.",
          image: "Logo_Horizontal_Yellow",
          site: "https://www.g-hitech.com/home",
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Fluitec",
          profil:
            "Elimination de consommation d'huiles lubrifiantes industrielles ('Fill4Life').",
          image: "Logo-Fluitec-Color-2020",
          site: "https://www.fluitec.com/",
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Entrepreneurs sans Frontières (OZG)",
          profil:
            "Entrepreneurs Sans Frontières (OZG) est impliqué dans l’Initiative de la Grande Muraille Verte du Sénégal, en plantant des forêts à grande échelle.",
          image: "logo-fr",
          site: "https://www.ozg.be/",
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "ABC CONTRACTING SA",
          profil:
            "Acteur majeur dans les projets clé en main dans le secteur de l'Energie en Afrique (EPC).",
          image: "logo-abc-contracting",
          site: "https://www.abccontracting.be",
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "GREENWIN",
          profil:
            "GreenWin est le pôle wallon des Cleantechs.",
          image: "greenwin",
          site: "https://www.greenwin.be",
        },
        // {
        //   secteur: "Énergie / Eau / Environement / Technologies propres",
        //   nom: "Allience pour l'Electricité Rurale",
        //   profil:
        //     "une industrie décentralisée des énergies renouvelables pour le 21ème siècle, activant les marchés pour des services énergétiques abordables.",
        //   image: "logo_are",
        //   site: "https://www.ruralelec.org",
        // },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "WATERLEAU GROUP",
          profil:
            "Du traitement des eaux usées à la récupération de l'eau. De la conception de l'usine à l'automatisation des processus. Nous déployonsles ressources de chaque goutte d'eau : eau pure, énergie et nutriments.",
          image: "waterleau",
          site: "https://www.waterleau.com/",
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "IMM - INTERNATIONAL MONTAGE MAINTENANCE",
          profil:
            "Construction de centrales électriques, depuis l’étude de faisabilité à la construction clé en mains des installations. Références dans 18 pays du continant Africain.",
          image: "imm",
          site: "https://www.imm.energy",
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "SOCIETE WALLONNE DES EAUX",
          profil: "SOCIETE WALLONNE DES EAUX.",
          image: "wallon",
          site: "https://www.swde.be",
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Siemens Energy",
          profil:
            "Nous proposons des produits, des solutions et des services sur l'ensemble de la chaîne de valeur de l'énergie.",
          image: "siemens-energy",
          site: "https://siemens-energy.com",
        },
        // {
        //   secteur: "Énergie / Eau / Environement / Technologies propres",
        //   nom: "Engie - Tractebel",
        //   profil:
        //     "A la tête de la transition énergétique, Tractebel offre une gamme complète de services couvrant l’ensemble du cycle de vie des projets dans les domaines de l'Energie, de l'Eau et des Infrastructures.",
        //   image: "engie",
        //   site: "https://www.engie.com",
        // },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Care4water",
          profil:
            "Désinfection/potabilisation de l'eau . Technologie innovante de production in-situ de chlore à partir de sel",
          image: "logo-c4water-gris",
          site: "https://www.c4water.com",
        },
        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Sotrad",
          profil:
            "Un ensemble de technologies innovantes de pompage, de traitement et de stockage d'eau.",
          image: "logo-dark-278w",
          site: "https://www.sotradwater.be",
        },

        {
          secteur: "Énergie / Eau / Environement / Technologies propres",
          nom: "Teconex",
          profil:
            " Producteur du Teco, référence belge indispensable au raccordement électrique depuis 1932.",
          image: "teconex",
          site: "https://teconex.eu",
        },
        {
          secteur:
            "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "UNITED PETFOOD",
          profil: "Fabricant d'aliments secs et humides, de biscuits et de snacks de qualité pour animaux de compagnie.",
          image: "unitedpetfood",
          site: "https://www.unitedpetfood.eu/",
        },
        {
          secteur:
            "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "KIPCO-DAMACO",
          profil: "TRANSFORMATION DES ALIMENTS: nous sommes l’un des plus importants producteurs au monde de viande de poulet et de dinde désossée. DISTRIBUTION ALIMENTAIRE & SCIENCE NUTRITIONNELLE.",
          image: "damaco-group",
          site: "https://www.damaco-group.com/",
        },
        {
          secteur:
            "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "CRODI",
          profil: "Recyclage des huiles de cuisson usagées, graisses brunes, huiles acides végétales, huiles spéciales et biomatériaux.",
          image: "cropped-CRODI-logo-transparant",
          site: "http://crodi.be/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "BEST FRIENDS",
          profil: "Elevage de chiens de sécurité et de garde.",
          image: "logo-best-friends",
          site: "https://www.bestfriends.be/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "BELORTA",
          profil:
            "Avec plus de 170 variétés de fruits et légumes, nous faisons de la nourriture saine.",
          image: "belorta",
          site: "https://www.belorta.be",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "GOOD !D",
          profil: "Nourriture pour animaux domestiques.",
          image: "hupple",
          site: "https://www.hupple.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "MOUSSA'S BISSAP",
          profil: "Boisson à base d'hibiscus et de menthe.",
          image: "bissap",
          site: "https://www.bis-sap.com",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "BEXPO",
          profil:
            "Grossiste spécialisé avec une très large gamme de produits alimentaires et de matériel de restauration.",
          image: "beeckman-logo-header",
          site: "https://beeckmanspices.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "FAIRY CHOCOLATES",
          profil: "Chocolats de qualités.",
          image: "fairychocolates",
          site: "https://www.fairychocolates.be/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Belourthe SA",
          profil: "Production de céréales et lait en poudre pour enfants.",
          image: "Belourthe",
          site: "http://www.belourthe.be",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Casa dimensa ASBL",
          profil:
            "Transformation des produits du terroir Sénégalais ( vinaigrettes de baobab).",
          image: "logo-01-500x500",
          site: "https://WWW.lacuisinedesuzanne.com",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Alston SRL",
          profil:
            "L'industrie alimentaire est notre spécialité, et nous nous engageons à offrir le plus haut niveau de service, tout en offrant à nos clients une large gamme de produits de la meilleure qualité de nos partenaire.",
          image: "cropped-Alston-Logo",
          site: "https://alstonex.com/",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Fresh & Saucy Foods",
          profil:
            "Sauces traditionnelles belges de haute qualité. Les produits sont commercialisés sous la propre marque authentique August & Henri et/ou sous private labelling.",
          image: "LOGO-AUGUSTHENRI",
          site: "http://www.augusthenri.be",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Gruut",
          profil: "Brasserie, spiritueux.",
          image: "gruut",
          site: "https://www.gruut.be",
        },
        // {
        //   secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
        //   nom: "Lady Agri",
        //   profil:
        //     "Investissement dans des projets agroindustriels ou les femmes contribuent, dirigent et gagnent.",
        //   image: "5e655f9f68556a76d63ce6d5_Logo_dark",
        //   site: "https://www.lady-agri.org/",
        // },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "TRIFERTO BELGIUM",
          profil: "Grossiste international en engrais minéraux.",
          image: "triferto",
          site: "https://www.triferto.eu",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "DUFINA",
          profil:
            "Dufina est une entreprise industruielle reconnues pour ses charcuteries salées, cuites et séchées de qualité artisanale.",
          image: "dufina",
          site: "https://www.dufina.be",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "LAMBERS-SEGHERS",
          profil:
            "Des aliments de qualité et une aide personnalisée pour les éleveurs et agriculteurs.",
          image: "lseg",
          site: "https://www.lambers-seghers.be",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "DUTY FREE WORLD SUPPLY",
          profil: "Vente de duty free aux Ambassades.",
          image: "duty",
          site: "https://www.dws-brussels.com",
        },
        {
          secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
          nom: "Cereal Tester",
          profil:
            "Spécialisé dans la vente, l'intallation d'instruments de laboratoire, de kit d'analyse pour l'agro-industrie et  l'agro-alimentaire.",
          image: "cerealtester",
          site: "https://www.cerealtester.com",
        },
        // {
        //   secteur: "Agriculture / Agroalimentaire / Aliments / Boissons",
        //   nom: "NEOBULLES",
        //   profil:
        //     "Vins désalcoolisés, bières alcoolisées et désalcoolisées, jus pétillants pour enfants .",
        //   image: "neobulles",
        //   site: "https://www.neobulles.be",
        // },
        // {
        //   secteur: "Services / Consultance",
        //   nom: "ACONTRARIO.LAW",
        //   profil: "Axé sur le droit commercial, la propriété intellectuelle, l'informatique et la protection des données, AContrario est un cabinet d'avocats d'affaires.",
        //   image: "Logo-AContrario-website-@2x",
        //   site: "https://acontrario.law/",
        // },
        {
          secteur: "Services / Consultance",
          nom: "Van Cutsem Wittamer Marnef & Partners",
          profil: "Services légaux , spécifiquement sur le marché africain.",
          image: "vancutsem",
          site: "http://www.vancutsem.be/",
        },
        {
          secteur: "Services / Consultance",
          nom: "SCHUMAN Associates",
          profil: "Conseil en affaires européennes.",
          image: "schuman-logo-web",
          site: "https://www.schumanassociates.com/",
        },
        {
          secteur: "Services / Consultance",
          nom: "PPMGL CONSULTING",
          profil:
            "Société de consultance spécialisée dans l’appui aux entreprises privées, publiques et aux organisations dans les domaines liés à l’amélioration des performances et des processus de gestion.",
          image: "ppmgl",
          site: "https://www.ppmgl.eu",
        },
        {
          secteur: "Services / Consultance",
          nom: "INEADEC",
          profil:
            "L’Institut Euro-Africain de Droit économique a pour objectif de favoriser le développement du droit économique en Afrique grâce à des colloques et séminaires d’étude conduisant à des publications.",
          image: "ineadec_logo",
          site: "https://www.ineadec.com",
        },
        {
          secteur: "ICT et électronique",
          nom: "EVS BROADCAST EQUIPEMENT",
          profil:
            "Notre technologie est utilisée dans le monde entier pour fournir les images sportives captivantes en direct et en temps réel à des milliards de téléspectateurs chaque jour.",
          image: "evs",
          site: "https://www.evs.com",
        },
        {
          secteur: "ICT et électronique",
          nom: "CREATIVE DISTRICT",
          profil:
            "Hub & Incubateur de l'innovation créative et sociale et du développement de l'entrepreneuriat.",
          image: "Logo-Creative-District-1024x272",
          site: "https://www.creative-district.be/",
        },
        {
          secteur: "ICT et électronique",
          nom: "FB CONSULTING GROUP",
          profil:
            "Nos équipes et nos partenaires fournissent une large gamme de services informatiques en Europe et en Afrique.",
          image: "fbcgroup",
          site: "https://www.fbcgroup.co",
        },
        {
          secteur: "Services / Consultance",
          nom: "OVO - ENTREPRENEURS POUR ENTREPRENEURS",
          profil:
            "L'esprit d'entreprise local est un moteur pour de plus grandes opportunités. Entrepreneurs for Entrepreneurs - OVO en abrégé - renforce l'entrepreneuriat durable en Afrique.",
          image: "ondernemersvoorondernemers",
          site: "https://www.ondernemersvoorondernemers.be",
        },
        {
          secteur: "Services / Consultance",
          nom: "DE BOECK MICHAEL",
          profil:
            "Notre équipe est prête à fournir des conseils juridiques de haute qualité sur tous les aspects du droit commercial européen et international",
          image: "EVEREST_ADR_Logo-239w",
          site: "http://www.eutradelawyer.com",
        },
        {
          secteur: "Services / Consultance",
          nom: "RODSCHINSON INVESTMENT GROUP",
          profil:
            "Nous conseillons et accompagnons les entreprises et les particuliers sur l’ensemble de leur parcours immobilier.",
          image: "Logo-ROD-White",
          site: "http://www.rodschinson.com",
        },
        {
          secteur: "Services / Consultance",
          nom: "T-LEX",
          profil:
            "Le cabinet T-LEX se positionne comme l’allié de ceux qui ambitionnent de devenir des acteurs économiques puissants sur le continent Africain.",
          image: "cropped-T-Lex-transparent-03-1024x935-1-1",
          site: "http://www.t-lex.law",
        },
        {
          secteur: "Services / Consultance",
          nom: "NINITEEN CONSULTING",
          profil: "Conseil en Management.",
          image: "bwma",
          site: "http://www.bwma.be/",
        },
        {
          secteur: "Services / Consultance",
          nom: "Ovation",
          profil:
            "Ovation est un centre de ressources pour les incubateurs et accélérateurs d’entreprises qui exploite les méthodes de créativité et d’innovation les plus efficaces. ",
          image: "Logo+Ovation+-+Vert+et+noir",
          site: "http://www.ovation.eco",
        },
        {
          secteur: "Services / Consultance",
          nom: "A-Law",
          profil:
            "Cabinet d'avocats international avec conseil juridique dans toutes les régions où vous cherchez de l'aide. ",
          image: "la-law",
          site: "https://www.a-law.eu",
        },
        {
          secteur: "Services / Consultance",
          nom: "Sunulex",
          profil:
            "Sunulex.africa, la plateforme digitale des droits africains offre un accès à plus de 70.000 documents légaux et fiscaux pour mieux préparer et/ou développer son activité économique en Afrique Francophone, par simple abonnement. ",
          image: "sunulex-logo-full",
          site: "http://www.sunulex.africa",
        },
        ,
        // {
        //   secteur: "Services / Consultance",
        //   nom: "Phalenes SA",
        //   profil: "PHALENES SA est une société européenne leader spécialisée depuis 1998 dans le domaine du développement international avec une expérience dans la fourniture et la gestion de services de conseil et d'assistance technique de haute qualité. ",
        //   image: "phales",
        //   site: "http://www.phalenes.org/",
        // },
        {
          secteur: "Services / Consultance",
          nom: "CMS DeBacker",
          profil: "Cabinet d'avocats d'affaire. ",
          image: "cmslaw",
          site: "https://www.cms.law",
        },
        {
          secteur: "Services / Consultance",
          nom: "Liedekerke Wolters Waelbroeck Kirkpatrick",
          profil: "Bureau d'Avocats ",
          image: "liedekerke",
          site: "https://liedekerke.com/",
        },
        {
          secteur: "Services / Consultance",
          nom: "Simont-Braun",
          profil:
            "Notre cabinet se concentre sur les services juridiques aux entreprises et je me consacre personnellement au droit des sociétés et aux fusions et acquisitions, ainsi qu'à l'arbitrage et aux litiges internationaux. ",
          image: "logo-simontbraun-new",
          site: "https://www.simontbraun.eu",
        },
        {
          secteur: "Services / Consultance",
          nom: "DECISIA",
          profil: "Centrale d'achat et consultance technique. ",
          image: "Logo-Procurafrica-def",
          site: "https://www.procurafrica.com",
        },
        // {
        //   secteur: "Services / Consultance",
        //   nom: "DIOUF & PARTNERS",
        //   profil:
        //     "Audit, Taxes et expertise comptable. ",
        //   image: "logo-simontbraun-new",
        //   site: "https://www.dioufpartners.com",
        // },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "VDC ENGINEERING",
          profil:
            "Nous sommes une équipe de 20 techniciens et experts dédiés à la conception, la mise en service, la qualification et la validation d'équipement dans l'industrie pharmaceutique et le secteur hospitalier.",
          image: "vdc-engineering",
          site: "https://www.vdc-engineering.com",
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "FMMP",
          profil:
            "Distribution, collaboration, représentation des produits pharmaceutiques, équipes médicales et device médical.",
          image: "FMMP-logo_final-3",
          site: "https://fmmp-medical.com/",
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "UNIZIMA",
          profil:
            "Univercells développe des technologies et des services qui démocratisent la production de produits biologiques. Pour que chacun, partout, ait accès aux médicaments dont il a besoin, quand il en a besoin.",
          image: "univercells",
          site: "https://www.univercells.com",
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "Ecosteryl",
          profil:
            "Unités de traitements des déchets Biomédicaux (DBM) par micro-ondes (processus ecologique). ",
          image: "ecosteryl",
          site: "http://www.ecosteryl.com",
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "AGFA RADIOLOGY SOLUTIONS",
          profil: "Imagerie médicale.",
          image: "Agfa_logo_color",
          site: "https://www.agfa.com",
        },
        // {
        //   secteur:
        //     "Médical / Pharmaceutique / Chimie",
        //   nom: "WORLD INFINITY SERVICES",
        //   profil: "World Infinity Services se consacre au transport et à la logistique des matières radioactives et des produits radiopharmaceutiques dans le monde entier.",
        //   image: "be-wis",
        //   site: "https://www.be-wis.com/fr/",
        // },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "ION BEAM APPLICATION",
          profil:
            "IBA développe, fabrique et maintient des dispositifs médicaux et solutions logicielles dédiés au diagnostic et au traitement du cancer.",
          image: "iba",
          site: "https://www.iba-worldwide.com",
        },
        // {
        //   secteur: "Médical / Pharmaceutique / Chimie",
        //   nom: "Medi-Earth",
        //   profil:
        //     "Réalisation de projets clé-en-main et la fourniture d’équipements dans le domaine de la santé. ",
        //   image: "medi",
        //   site: "https://medi-earth.be/",
        // },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "Unizima Univercells",
          profil:
            "Chez Unizima, nous nous associons à nos clients pour proposer des projets clés en main qui prennent en charge tous les aspects de la conception et de la mise en place d'installations et de processus de bioproduction et de systèmes de santé tels que des diagnostics précoces et des centres de traitement spécialisés. ",
          image: "Logo-Unizima",
          site: "https://unizima.com/",
        },

        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "MULTI-G",
          profil:
            "Multi-G est un laboratoire pharmaceutique implanté en Afrique francophone depuis 30 ans. Notre mission: des médicaments de qualité et abordables pour toutes les populations africaines.",
          image: "multi-g",
          site: "https://www.multi-g.com",
        },
        // {
        //   secteur:
        //     "Médical / Pharmaceutique / Chimie",
        //   nom: "Zenith Afrique",
        //   profil: "Consultation liée à la réglementation scientifique, pharmaceutique et biotechnologique.",
        //   image: "Zenith-Care-logo1",
        //   site: "https://www.scimedservices.com",
        // },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "BIO-SOURCING",
          profil:
            "Nouvelle génération de produits biothérapeutiques pour les besoins médicaux mondiaux.",
          image: "bio-sourcing",
          site: "https://www.bio-sourcing.com",
        },
        {
          secteur: "Médical / Pharmaceutique / Chimie",
          nom: "REMED PHARMA",
          profil:
            "Production de différentes gammes de préservatifs pour contribuer à la protection de chacun contre les infections sexuellement transmissibles, mais aussi afin d'offrir des produits sûrs dans le cadre de la planification familiale.",
          image: "remed",
          site: "https://www.remedpharma.com",
        },
        // {
        //   secteur:
        //     "Médical / Pharmaceutique / Chimie",
        //   nom: "SciMed Services & Solutions",
        //   profil: "La société SciMed Services & Solutions est active dans le developpement et la commercialisation des kits de diagnostic pour les maladie infectieuses. La société offre aussi des consultations relatives à la réglementation scientifique, pharmaceutique et biotechnologique.",
        //   image: "ScieMed26S_edited",
        //   site: "https://www.scimedservices.com",
        // },
        // {
        //   secteur:
        //     "Produits chimiques / produits pharmaceutiques / sciences de la vie",
        //   nom: "Aciers Grosjean",
        //   profil:
        //     "Achat et vente de produits en acier excédentaire ou déclassé. Acier laminé à chaud ou à froid, bobines galvanisées, tôles prélaquées, bandes électrozinguées… ",
        //   image: "cropped-logo-GrosJeanST-RGB",
        //   site: "https://grosjeansteeltrading.com/",
        // },
        // {
        //   secteur:
        //     "Produits chimiques / produits pharmaceutiques / sciences de la vie",
        //   nom: "VM Steel (anciennement Van Meerbeeck Export)",
        //   profil:
        //     "Commercialisation d'acier carbone et inoxydable, partout dans le monde. ",
        //   image: "vm-steel-logo",
        //   site: "https://vmsteel.com/",
        // },
        // {
        //   secteur: "Metallurgie",
        //   nom: "Aciers Grosjean",
        //   profil:
        //     "Achat et vente de produits en acier excédentaire ou déclassé. Acier laminé à chaud ou à froid, bobines galvanisées, tôles prélaquées, bandes électrozinguées… ",
        //   image: "cropped-logo-GrosJeanST-RGB",
        //   site: "https://grosjeansteeltrading.com/",
        // },
        // {
        //   secteur: "Metallurgie",
        //   nom: "VM Steel (anciennement Van Meerbeeck Export)",
        //   profil:
        //     "Commercialisation d'acier carbone et inoxydable, partout dans le monde. ",
        //   image: "vm-steel-logo",
        //   site: "https://vmsteel.com/",
        // },
        // {
        //   secteur: "Metallurgie",
        //   nom: "ZINGAMETALL",
        //   profil:
        //     "ZINGA® se distingue d’autres systèmes anticorrosion par un système de film galvanisant avec une application aisée, qui offre non seulement une protection cathodique active mais également une protection passive. ",
        //   image: "zinga_200h",
        //   site: "https://www.zinga.be",
        // },
        {
          secteur: "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "TECHNC",
          profil:
            "Nettoyage interne des moteursà l'hydrogène.",
          image: "logo-technc-2",
          site: "http://technc.be/",
        },
        {
          secteur:
            "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "NOËL & MARQUET – A BRAND OF NMC",
          profil:
            "NOËL & MARQUET est une marque de design d'intérieur haut de gamme. Des plinthes aux cimaises, corniches, profils d'éclairage, panneaux muraux 3D et bien plus encore, NOËL & MARQUET permet des solutions créatives et uniques pour la décoration des sols, des murs et des plafonds. ",
          image: "nmc",
          site: "https://noel-marquet.net/fr/",
        },
        {
          secteur:
            "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "TD WILLIAMSON",
          profil:
            "TDW fournit des solutions pour les systèmes de tuyauterie sous pression pour les applications onshore et offshore.",
          image: "header image white 2x",
          site: "https://www.tdwilliamson.com",
        },
        {
          secteur:
            "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "ALPHATRONICS",
          profil:
            "Fabricant de barrières automatiques, lecteurs de badges RFID, systèmes de parking, tourniquets – tambours rotatifs et autres systèmes de contrôle d’accès.",
          image: "alphatronics",
          site: "https://www.alphatronics.be/nl/home",
        },
        {
          secteur:
            "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "FASSADA SYTEMS",
          profil:
            "solutions de murs-rideaux en aluminium et en acier pour les bâtiments commerciaux et de grande hauteur.",
          image: "fassada",
          site: "https://www.fassada.com",
        },
        {
          secteur:
            "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "DAIKIN EUROPE",
          profil:
            "Solutions de climatisation, chauffage et conditionnement d'air.",
          image: "daikin",
          site: "https://www.daikin.eu",
        },
        {
          secteur:
            "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "4M EUROPE",
          profil: "Sols en résine epoxy antidérapant.",
          image: "logo-4m",
          site: "https://www.4mgroup.com ",
        },
        {
          secteur:
            "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Convergent Group",
          profil:
            "Produits de traitement et de revêtment des sols industriels.",
          image: "convergent-group",
          site: "https://www.convergent-group.com",
        },
        // {
        //   secteur:
        //     "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
        //   nom: " AGC GLASS EUROPE",
        //   profil:
        //     "Leader mondial en verre plat, AGC Glass Europe contribue à révéler les potentialités du verre plat au profit de la construction, de l'automobile, des transports, du solaire et du high-tech. Pour les Smart Cities AGC propose des solutions allant du verre à contrôle solaire dynamique à l’antenne 5G intégrée au vitrage. ",
        //   image: "agc",
        //   site: "https://www.agc-glass.eu",
        // },
        {
          secteur:
            "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Anglo Belgian Corporation NV (ABC)",
          profil:
            "Depuis 1912, fabricant belge moteurs semi-lents multi fuels (1-10MW) - Electrification (Exemple: Centrale thermique des GMD avec moteurs ABC, etc.) ",
          image: "logo-abc@2x",
          site: "https://www.abc-engines.com",
        },
        // {
        //   secteur:
        //     "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
        //   nom: "KSB Belgium SA/NV",
        //   profil:
        //     "Fabricant de pompes et robinetterie,nous livrons clés en main la partie hydromécanique des stations de pompage des projets d'adductions d'eau. ",
        //   image: "ksb",
        //   site: "https://www.ksb.com",
        // },
        {
          secteur:
            "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "JD EUROPE",
          profil:
            "Machines de génie civil,groupe électrogènes et équipements plus export véhicules neufs Toyota officiel pour l'Afrique.",
          image: "jd-europe",
          site: "https://www.jd-europe.com",
        },
        {
          secteur:
            "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "ODM (Outilac De Munter) ",
          profil:
            "Outillage professionnel standards et spécifiques pour l'industrie.",
          image: "odm",
          site: "https://www.odm.eu",
        },
        {
          secteur:
            "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "ANDEX-RENT",
          profil:
            "Andex est spécialisé dans le sourcing des voitures pour les clients B2B.",
          image: "andex",
          site: "https://www.andex-rent.be",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénierie",
          nom: "ASPAC TECHNICS",
          profil:
            "EAU POTABLE (captage, traitement, le pompage, stockage, la distribution) EAUX USÉES;  RÉDUCTION DES EAUX NON GÉNÉRATRICES DE REVENUS; FINANCEMENT DE PROJETS.",
          image: "aspac-technics",
          site: "https://aspac-technics.com",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénierie",
          nom: "ATELIER D'ARCHITECTURE GALAND",
          profil: "Architecte.",
          image: "atelier",
          site: "https://www.atelier-architecture-galand.be ",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénierie",
          nom: "SCE",
          profil:
            "SCE est l'expert indépendant pour les bâtiments pour meunerie et provenderie. Silos à grains.",
          image: "sce",
          site: "https://www.sce.be",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénierie",
          nom: "JOHN COCKERILL",
          profil:
            "Animé depuis 1817 par l’esprit d’entreprendre et la soif d’innover de son fondateur, le Groupe John Cockerill met au point des solutions technologiques à grande échelle pour répondre aux besoins de son temps.",
          image: "cockerill-logo",
          site: "https://www.johncockerill.com",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénierie",
          nom: "BESIX",
          profil:
            "Entreprise multidisciplinaire dans la construction, la promotion immobilière et concessions.",
          image: "BESIX-logo",
          site: "https://www.besix.be",
        },
        {
          secteur:
            "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Continental Materials Supply",
          profil:
            "Fourniture de matériel au secteur minier, pétrochimique et industriel.",
          image: "cms",
          site: "https://www.cmsantwerp.eu",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénierie",
          nom: "Achitecte SOMERS",
          profil: "Architecte et Urbaniste & ingénierie et design.",
          image: "somers",
          site: "https://somersespace.wixsite.com/website",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénierie",
          nom: "DREDGING INTERNATIONAL",
          profil:
            "Travaux marins, dragage, construction, infrastructure, Engineering.",
          image: "dem-groupe",
          site: "https://www.deme-group.com",
        },

        {
          secteur: "Construction services / Infrastructure / Ingénierie",
          nom: "FRISOMAT",
          profil: "Construction de batiments industriels.",
          image: "frisomat",
          site: "https://www.frisomat.com",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénierie",
          nom: "SIEMENS",
          profil:
            "Smart Infrastructure de Siemens connecte les systèmes d'énergie, les technologies des bâtiments et les industries pour former une infrastructure intelligente qui s'adapte à notre manière de vivre et de travailler et évolue avec elle.",
          image: "siemens",
          site: "https://www.siemens.com/global/en.html",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénierie",
          nom: "JAN DE NUL",
          profil:
            "Travaux marins, dragage, construction, infrastructure, Engineering.",
          image: "jdn",
          site: "https://www.jandenul.com",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénierie",
          nom: "Recon Group",
          profil:
            "Entreprise de construction de logements et projets immobiliers.",
          image: "recon-group",
          site: "https://www.recongroup.be",
        },
        {
          secteur: "Construction services / Infrastructure / Ingénierie",
          nom: "FSE",
          profil:
            "Réalisation de projets d’équipements biomédicaux et de laboratoires à l’international.",
          image: "logo-light-couleur-blanc-retina",
          site: "https://www.fse-export.com",
        },
        {
          secteur:
            "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Carmeuse",
          profil: "Production & Commercialisation de chaux. ",
          image: "carmeuse",
          site: "https://www.carmeuse.be",
        },
        {
          secteur:
            "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "Aciers Grosjean",
          profil:
            "Achat et vente de produits en acier excédentaire ou déclassé. Acier laminé à chaud ou à froid, bobines galvanisées, tôles prélaquées, bandes électrozinguées… ",
          image: "cropped-logo-GrosJeanST-RGB",
          site: "https://grosjeansteeltrading.com/",
        },
        {
          secteur:
            "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "VM Steel (anciennement Van Meerbeeck Export)",
          profil:
            "Commercialisation d'acier carbone et inoxydable, partout dans le monde. ",
          image: "vm-steel-logo",
          site: "https://vmsteel.com/",
        },
        {
          secteur:
            "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "DIMEXCO GROUP",
          profil:
            "Dimexco Group, votre partenaire d’équipement minier et industriel depuis plus de 30 ans.",
          image: "620f6b012e46748225895645_Original20Transparent-p-500",
          site: "https://www.dimexco.be/",
        },
        {
          secteur:
            "Matériaux construction / Machines / Véhicules / Equipements / Outillage",
          nom: "ZINGAMETALL",
          profil:
            "ZINGA® se distingue d’autres systèmes anticorrosion par un système de film galvanisant avec une application aisée, qui offre non seulement une protection cathodique active mais également une protection passive. ",
          image: "zinga_200h",
          site: "https://www.zinga.be",
        },
        {
          secteur: "Transport et logistique",
          nom: "FOODCAREPLUS LOGISTICS)",
          profil:
            "Foodcareplus est un fournisseur intégré de services logistiques et d’accès aux marchés internationaux, actif dans l’industrie alimentaire.",
          image: "foodcareplus.remant",
          site: "http://foodcareplus.remant.be",
        },
        {
          secteur: "Transport et logistique",
          nom: "UNI-FORWARDING INTERNATIONAL (UFI)",
          profil:
            "UFI propose des solutions de chaîne d'approvisionnement avec une logistique intégrée et organise des expéditions de fret à l'échelle mondiale.",
          image: "unifor",
          site: "https://www.unifor.be",
        },
        {
          secteur: "Transport et logistique",
          nom: "SARENS",
          profil:
            "Leader mondial et référence dans les services de location de grues, de levage lourd et de transport technique.",
          image: "ssarens",
          site: "https://www.sarens.com/",
        },
        {
          secteur: "Transport et logistique",
          nom: "VECTURIS",
          profil: "VECTURIS.",
          image: "logo_bigger",
          site: "http://www.vecturis.com",
        },
        {
          secteur: "Transport et logistique",
          nom: "HERFURTH LOGISTICS",
          profil:
            "Herfurth Logistics est une société de transit et de logistique internationale ayant ses racines en Europe et présente sur le marché depuis plus de 100 ans.",
          image: "herfurth_logistics-h30",
          site: "https://www.herfurth-logistics.com",
        },
        {
          secteur: "Transport et logistique",
          nom: "AFRIQUE ENERGIES NOUVELLES",
          profil:
            "Nous vous offrons un cadre agréable de formation associant théorie et pratique, et également en mode apprentissage projet, avec du matériel de pointe pour chaque filière de formation.",
          image: "enr-academyl",
          site: "https://www.enr-academy.com/",
        },
        {
          secteur: "Transport et logistique",
          nom: "Omnifreight",
          profil: "Transit International, Freight Forwarding.",
          image: "omnifreight_logo",
          site: "http://www.omnifreight.eu/",
        },
        {
          secteur: "Transport et logistique",
          nom: "TUI FLY",
          profil: "Opérateur aérien et voyage.",
          image: "tui",
          site: "http://www.tui.be",
        },
        {
          secteur: "Transport et logistique",
          nom: "Africa ports and airports Benelux",
          profil:
            "Partenaire privilégié pour des solutions portuaires et logistiques et spécialisé dans les projets miniers, pétroliers, gaziers.",
          image: "logo-Africa-Ports-Airports-blanc-260x78px",
          site: "http://www.africa-port.com",
        },
        {
          secteur: "Transport et logistique",
          nom: "CARAVEL INTERNATIONAL",
          profil:
            "Caravel International fournit dans le monde entier des services logistiques sur mesure en partenariat étroit avec nos clients.",
          image: "Shipping-and-freight-CARAVEL-International-Brecht-001-191w",
          site: "https://www.caravel.be",
        },
        // {
        //   secteur: "Transport et logistique",
        //   nom: "Sarens",
        //   profil:
        //     "sarens est le leader mondial et la référence des services de location de grues, de levage de charges lourdes et de transport technique pour nos clients.",
        //   image: "ssarens",
        //   site: "https://www.sarens.com",
        // },
        // {
        //   secteur: "Transport et logistique",
        //   nom: "NHV Helicopters",
        //   profil:
        //     "NHV Group, dont le siège est à Ostende en Belgique, est spécialisé dans les services d'hélicoptères B-to-B et a une forte présence géographique en Europe et en Afrique de l'Ouest.",
        //   image: "nhv",
        //   site: "https://nhv.be/",
        // },
        {
          secteur: "Transport et logistique",
          nom: "Conti-Lines",
          profil:
            "Nous sommes spécialisés dans le transport maritime à l'aide d'une flotte de vraquiers de petite taille à ultramax.",
          image: "CL-RGB150",
          site: "https://www.contilines.be",
        },

        {
          secteur: "Transport et logistique",
          nom: "SEA-INVEST",
          profil:
            "Opérateurs de terminaux portuaires pour le vrac sec, les fruits et le vrac liquide.",
          image: "sea-invest",
          site: "https://www.sea-invest.com",
        },
        {
          secteur: "Transport et logistique",
          nom: "Brussels Airlines",
          profil:
            "Brussels Airlines est la compagnie aérienne nationale belge et dessert plus de 120 destinations.",
          image: "brusselsairlines",
          site: "https://www.brusselsairlines.com",
        },
        {
          secteur: "Transport et logistique",
          nom: "DAXI",
          profil:
            "Nous fabriquons, distribuons et recyclons le matériel ferroviaire.",
          image: "_DAXI",
          site: "http://www.daxi.be",
        },
        {
          secteur: "Transport et logistique",
          nom: "PORT OF ANTWERP-BRUGES INTERNATIONAL (POABI)",
          profil:
            "POABI conjugue son expérience dans l'un des plus grands ports du monde, pour vous accompagner dans vos démarches de conception, d'extension ou de renouvellement de votre projet.",
          image: "PAI_Logo_pos_rgb",
          site: "https://www.portofantwerpinternational.com",
        },
        {
          secteur: "Transport et logistique",
          nom: "REMANT AFRICA LOGISTICS",
          profil:
            "Nous vous proposons  40 ans d’expérience et de savoir-faire sur l’entièreté du parcours d’expédition. Nos Architectes du Transport tracent pour vous, de A à Z, le parcours logistique optimal.",
          image: "remana",
          site: "https://africa.remant.be/",
        },
        {
          secteur: "Transport et logistique",
          nom: "TRAFIQURAIL",
          profil:
            "Exploitation et transport ferroviaire de produits miniers, agricoles, fret commercial et voyageurs.",
          image: "logo-website1-300x125",
          site: "http://www.trafiqurail.com/en/",
        },
        {
          secteur: "Éducation",
          nom: "ACADÉMIE DE RECHERCHE ET D'ENSEIGNEMENT SUPÉRIEUR - ARES – ARES",
          profil:
            "...sensibiliser et former aux enjeux de la transition écologique et du développement durable dans l’enseignement supérieur.",
          image: "Ares-logo",
          site: "https://www.ares-ac.be",
        },
        {
          secteur: "Éducation",
          nom: "ESA SAINT-LUC BRUXELLES",
          profil:
            "L'ESA Saint-Luc Bruxelles* est un lieu d'enseignement et un atelier de création et de production où se forgent des générations d'artistes et d'auteurs de projets.",
          image: "stluc",
          site: "http://www.stluc-bruxelles-esa.be/-International-?presentation=fr",
        },
        {
          secteur: "Éducation",
          nom: "HAUTE ÉCOLE DE LA PROVINCE DE LIÈGE",
          profil: "Un enseignement ouvert à chacun pour l'avenir de tous !",
          image: "hepl",
          site: "https://www.hepl.be/fr",
        },
        {
          secteur: "Éducation",
          nom: "HAUTE ÉCOLE EPHEC",
          profil: "Le chemin pratique vers la réussite.",
          image: "ephec",
          site: "https://www.ephec.be",
        },
        {
          secteur: "Éducation",
          nom: "HAUTE ÉCOLE FRANCISCO FERRER",
          profil: "MON HE-FERRER ,le portail pour vous faciliter les études.",
          image: "Logo HEFF_0",
          site: "https://www.ephec.be",
        },
        {
          secteur: "Éducation",
          nom: "HAUTE ÉCOLE LÉONARD DE VINCI",
          profil:
            "La Haute Ecole Vinci propose des formations uniques en Belgique grâce à la combinaison d’entités de pointe et complémentaires, le tout dans un environnement à taille humaine.",
          image: "vinci",
          site: "http://www.vinci.be/",
        },
        {
          secteur: "Éducation",
          nom: "HAUTE ÉCOLE LIBRE DE BRUXELLES - ILYA PRIGOGINE",
          profil:
            "L'asbl, dont le siège social est établi au Bâtiment HA du Campus de la Plaine (Boulevard du triomphe, accès 2 – CP 220/01 à 1050 Bruxelles), a pour but d’organiser de l’enseignement.",
          image: "en-tete_2040x340",
          site: "https://www.helb-prigogine.be/",
        },
        {
          secteur: "Éducation",
          nom: "HAUTE ÉCOLE LOUVAIN EN HAINAUT - HELHA",
          profil:
            "La HELHa propose des études supérieures professionnalisantes (du Bachelier au Master) : 60 formations réparties sur Braine-le-Comte, Charleroi, Gilly, Gosselies, La Louvière, Leuze-en-Hainaut, Louvain-La-Neuve, Loverval, Mouscron, Mons, Montignies-sur-Sambre et Tournai.",
          image: "helha",
          site: "https://www.helha.be/",
        },
        {
          secteur: "Éducation",
          nom: "IHECS - HAUTE ÉCOLE GALILÉE",
          profil:
            "Depuis 1958, l'Institut des Hautes Études des Communications Sociales (IHECS) organise des formations dans le domaine du journalisme et de la communication en articulant théorie et pratique des médias en plein coeur de Bruxelles (Belgique).",
          image: "ihecs",
          site: "https://www.ihecs.be/",
        },
        {
          secteur: "Éducation",
          nom: "KU LEUVEN",
          profil:
            "La KU Leuven est une communauté internationale où la recherche innovante constitue la base de tous nos programmes académiques. Dans toute l'université, des chercheurs motivés et des étudiants curieux acquièrent continuellement de nouvelles connaissances et utilisent leurs connaissances pour relever les principaux défis de notre époque.",
          image: "leuven",
          site: "https://www.kuleuven.be/kuleuven/",
        },
        {
          secteur: "Éducation",
          nom: "THOMAS MORE KEMPEN",
          profil: "THOMAS MORE KEMPEN",
          image: "thomas",
          site: "https://www.thomasmore.be/",
        },
        {
          secteur: "Éducation",
          nom: "ULB-COOPERATION",
          profil:
            "ULB-Coopération est l’ONG de l’Université libre de Bruxelles. Ses actions se localisent au Burkina Faso, en République démocratique du Congo, au Sénégal et en Belgique.",
          image: "ulb",
          site: "https://www.ulb-cooperation.org/",
        },
        {
          secteur: "Éducation",
          nom: "UNIVERSITÉ CATHOLIQUE DE LOUVAIN",
          profil:
            "L'UCLouvain, université internationale engagée dans la société: une multitude de services, des opportunités d'emploi et un espace alumni.",
          image: "uclouvain",
          site: "http://www.uclouvain.be/",
        },
        {
          secteur: "Éducation",
          nom: "UNIVERSITÉ DE LIÈGE",
          profil:
            "Une nouvelle année riche en projets pour l'équipe des MOOC's, avec en ligne de mire 500.000 apprenantes et apprenants au compteur. L'enseignement en ligne et ouvert à tous de l'ULiège poursuit sa croissance et continue d'élargir son catalogue dans de nombreux domaines du savoir.",
          image: "liege",
          site: "https://www.uliege.be/cms/c_8699436/fr/uliege",
        },
        {
          secteur: "Éducation",
          nom: "UNIVERSITÉ LIBRE DE BRUXELLES",
          profil:
            "L'ULB est localisée sur plusieurs campus et sites à Bruxelles et en Wallonie. Découvrez pour chacun les plans des campus ainsi que toutes les informations d'accès par mode de transport.",
          image: "ulbbruxell",
          site: "https://www.ulb.be/",
        },
        {
          secteur: "Éducation",
          nom: "UNIVERSITEIT GENT",
          profil:
            "L'Université de Gand est une université belge de renommée internationale, ouverte, pluraliste et socialement engagée.",
          image: "gent",
          site: "http://www.ugent.be/",
        },
        {
          secteur: "Éducation",
          nom: "UNIVERSITEIT HASSELT",
          profil: "UNIVERSITEIT HASSELT.",
          image: "50-jaar-uhasselt",
          site: "http://www.uhasselt.be/",
        },
        {
          secteur: "Éducation",
          nom: "Neo-Tech SA",
          profil:
            "Equipements didactiques scientifiques et techniques pour l'enseignement, la formation professionnelle, grandes écoles et universités, laboratoires de recherche et contrôle.",
          image: "neotech",
          site: "https://www.neo-tech.be",
        },
        {
          secteur: "Éducation",
          nom: "Televic",
          profil:
            "Televic Education est un leader mondial dans le développement de solutions basées sur la recherche qui aident à résoudre les problèmes de formation, de qualité, de certification, d'accréditation, d'évaluation permanente et de collaboration dans une variété d'industries.",
          image: "televic",
          site: "https://www.televic.com/education",
        },
        {
          secteur: "Éducation",
          nom: "D-TEACH",
          profil:
            "cours en ligne, ce qui est aussi rapide, flexible, international et multiculturel.",
          image: "d-teach-school_w250",
          site: "https://www.d-teach.com",
        },
        // {
        //   secteur: "Luxe / Textile / Mode / Bien-être",
        //   nom: "Amina fashion",
        //   profil:
        //     "Amina fashion vente de tissus ceremonie en gros et details .",
        //   image: "AminaFashion",
        //   site: "https://www.facebook.com/aminafashionadjana/",
        // },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "MUHIRE",
          profil:
            "Muhire est une fusion entre les influences européennes et l'esthétique tribale de la culture africaine.",
          image: "muhire_180_black",
          site: "https://www.muhire.eu/",
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "BY LA NATURE",
          profil:
            "Création et vente de soins cosmétiques naturels spécifiques (antifongiques et régénérants pour les ongles et la peau). Compléments alimentaires végan spécifiques et anti-âge.",
          image: "nature",
          site: "https://www.bylanature.eu",
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "AWA B. by Les Moussors d'Awa",
          profil:
            "Confection de moussor, turban prêt-à-porter, à toutes occasion et de vêtements unisexe avec de la broderie à la main. Organisatino d'ateliersthématiques.",
          image: "3de814_148f18856301488eafc065df4a055cd0_mv2_150x",
          site: "https://www.lesmoussorsdeawa.com",
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "POMANDI",
          profil:
            "Nous sommes des concepteurs de modèles de costumes, d’accessoires et de chaussures, costumes de marié et les costumes concept comme le style « Peaky Blinders », le style Crooners, le style vintage,.. ",
          image: "pomandi",
          site: "https://www.pomandi.com",
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "IFRANE",
          profil: "Cosmétiques - parfumerie. ",
          image: "ifrane",
          site: "https://www.ifrane.be",
        },
        {
          secteur: "Luxe / Textile / Mode / Bien-être",
          nom: "NEFALINE",
          profil:
            "Estheticienne spécialisée (traitement de la peau) - Infirmière.",
          image: "nefaline-ixelles-logo-8d999f97",
          site: "https://www.nefaline.eu",
        },
        // {
        //   secteur: "Services financiers",
        //   nom: "Belgian Bankers Academy",
        //   profil:
        //     "Conseil pour le development du secteur bancaire, de la finance, des assurances et de la micro finance .",
        //   image: "share",
        //   site: "https://www.bbacademy.be",
        // },
        {
          secteur: "Services financiers",
          nom: "CREDENDO",
          profil:
            "Credendo propose la couverture de risques d'exportation et d'investissement dans le monde entier, mais offre également des solutions de financement tant pour les PME que les grandes entreprises. ",
          image: "credendo",
          site: "https://www.credendo.com",
        },
        {
          secteur: "Services financiers",
          nom: "SOCIETE BELGE D'INVESTISSEMENT INTERNATIONAL",
          profil:
            "Cofinancer à moyen ou à long terme les investissements à l’étranger d’entreprises belges. ",
          image: "bmi-sbi",
          site: "https://www.bmi-sbi.be",
        },
        {
          secteur: "Services financiers",
          nom: "BIO Invest",
          profil:
            "BIO investit directement et indirectement dans des PME dans les pays en développement et apporte ainsi une contribution structurelle à la croissance socio-économique des pays d’accueil. ",
          image: "BIO-Tagline-Colour",
          site: "https://www.bio-invest.be",
        },
        {
          secteur: "Services financiers",
          nom: "KBC BANK",
          profil:
            "Nous sommes un groupe de bancassurance intégré, s'adressant principalement à une clientèle de particuliers, de banque privée, de PME et d'ETI. ",
          image: "kbc",
          site: "https://www.kbc.com",
        },
        {
          secteur: "ICT et électronique",
          nom: "CUBEWISE BELGIUM",
          profil:
            "Services aux entreprises en matière de planification et de reporting financiers, ainsi que de gestion de la chaîne d’approvisionnement. ",
          image: "cubewise",
          site: "https://www.cubewise.com",
        },
        // {
        //   secteur: "ICT et électronique",
        //   nom: "Njaheut",
        //   profil:
        //     "Prestation de services audio visuels et artistique.",
        //   image: "njaheut",
        //   site: "https://www.njaheut.com",
        // },
        {
          secteur: "ICT et électronique",
          nom: "SAFETY PRODUCT",
          profil: "Poteau pour la sécurité routière - Zip-Pole.",
          image: "SafetyProduct-1024x341",
          site: "https://www.safety-product.eu",
        },
        {
          secteur: "ICT et électronique",
          nom: "OCTOPUS DATA",
          profil: "Architecture Réseau & Cybersecurite.",
          image: "octopusdata",
          site: "https://www.octopusdata.be",
        },
        {
          secteur: "ICT et électronique",
          nom: "MACQ",
          profil:
            "Macq est une entreprise familiale belge fournissant des produits hautement fiables et innovants pour des applications haut de gamme dans le secteur Smart Mobility & ITS dans le monde entier. Nous nous distinguons en développant le logiciel et le matériel en interne, ce qui nous donne la liberté d'adapter facilement nos produits aux besoins de nos clients. ",
          image: "MacqMobility",
          site: "https://www.macq.eu",
        },
        {
          secteur: "ICT et électronique",
          nom: "MY ENGINEERING",
          profil:
            "Forts de plus de 10 ans d'expérience en ingénierie et gestion de projets dans l'industrie belge, Giovanni Mantione et Jimmy Vandenbranden ont décidé de fonder My engineering en 2017. Habitués à faire face à des environnements très exigeants, leur objectif est de vous permettre d'atteindre vos objectifs à terme. de coût, de délais et de qualité pour chacun de vos projets.",
          image: "logo-my-engineering-website",
          site: "https://www.my-engineering.be",
        },

        {
          secteur: "ICT et électronique",
          nom: "DCE sprl",
          profil:
            "DCE est une société qui vend des produits KNX, dispose d'un centre de formation et est également un bureau d'études.",
          image: "dce-logo-1597069812",
          site: "https://www.dce.be",
        },
        {
          secteur: "ICT et électronique",
          nom: "OTN SYSTEMS",
          profil:
            "Réseaux pour l'industrie, en ce compris les métros, les tramways, les télécoms, le pétrole et le gaz, les services publics d'électricité et l'exploitation minière.",
          image: "otnsystems",
          site: "https://www.otnsystems.com",
        },
        {
          secteur: "ICT et électronique",
          nom: "VIASAT CONNECT",
          profil: "Tracking, géolocalisation, workforce et fleet management.",
          image: "connect-bianco@2x",
          site: "https://www.viasatconnect.be",
        },
        {
          secteur: "ICT et électronique",
          nom: "NIXXIS",
          profil:
            "Solution Logicielle pour centre d'appel et centre de contacts. ",
          image: "Nixxis_Logotype_RGB-1-300x51",
          site: "https://www.nixxis.com",
        },
        {
          secteur: "Industries culturelles et créatives / loisirs / Tourisme",
          nom: "WALLIMAGE",
          profil:
            "Communication Manager - Film Commissioner.",
          image: "wallimage",
          site: "http://www.wallimage.be/",
        },
        {
          secteur: "Industries culturelles et créatives / loisirs / Tourisme",
          nom: "Spring Games",
          profil:
            "Jeux de société qui met en lumière les grandes richesses culturelles du continent au travers de 5 univers thématiques: Arts, Sports, Nature, Histoire et Géographie.",
          image: "Le+tour+d'Afrique-logo",
          site: "https://www.letourdafrique.com",
        },
        {
          secteur: "Industries culturelles et créatives / loisirs / Tourisme",
          nom: "FYNICC - FONDATION YOUSSOU NDOUR",
          profil:
            "Industries Culturelles et Créatives.",
          image: "fynicc",
          site: "https://www.fynicc.org/",
        },
        {
          secteur: "Industries culturelles et créatives / loisirs / Tourisme",
          nom: "CREATIVE AFRICA",
          profil:
            "Nous vous présentons des artistes, designers et acteurs culturels de l'Afrique Noire et de sa diaspora.",
          image: "LOGO-NOIR-CONCEPT-BLANC",
          site: "https://www.noirconcept.art/",
        },
        {
          secteur: "Industries culturelles et créatives / loisirs / Tourisme",
          nom: "FESTIVAL INTERNATIONAL DU FILM DE BRUXELLES (FIFB)",
          profil:
            "Festival accessible au grand public, aux plus grands professionnels du monde du cinéma et qui offre la possibilité de promouvoir les jeunes talents.",
          image: "logo-fifb-noir",
          site: "https://www.FIFB.BE",
        },
        {
          secteur: "Industries culturelles et créatives / loisirs / Tourisme",
          nom: "IndigoMood films",
          profil:
            "Documentaire, fiction, arts visuels, Indigo Mood accompagne les auteurs dans leurs désirs de création, porte leurs histoires, leurs sensibilités, leurs visons du monde, de la page blanche à l’écran, petit ou grand.",
          image: "LOGO-SITE-TEMP",
          site: "https://www.indigomoodfilms.com",
        },
        {
          secteur: "Industries culturelles et créatives / loisirs / Tourisme",
          nom: "PHRENOS",
          profil:
            "Organisateurs du Forum de Dakar avec Youssou N'dour.SOUHAIT: Contacts multiples, institutionnels et privés, pour développer le programme du Forum de Dakar#2 ",
          image: "phrenos",
          site: "https://www.phrenos.eu/en/",
        },

        // {
        //   secteur: "Industries culturelles et créatives / loisirs / Tourisme",
        //   nom: "Alina Assenova",
        //   profil: "Artiste peintre",
        //   image: "a4-alina",
        //   site: "https://alinaassenova.webnode.es/cuando-y-donde/",
        // },
        {
          secteur: "Industries culturelles et créatives / loisirs / Tourisme",
          nom: "MYCO Group",
          profil:
            "Système de réservation en ligne pour les agences de voyages.Lits bancaires pour hôtels. ",
          image: "mygo",
          site: "https://www.mygo.pro",
        },
        // {
        //   secteur: "Électricité",
        //   nom: "Teconex",
        //   profil:
        //     "Producteur du Teco, référence belge indispensable au raccordement électrique depuis 1932.",
        //   image: "teconex",
        //   site: "https://teconex.eu/fr",
        // },
        {
          secteur: "Services / Consultance",
          nom: "D’HAEYER law",
          profil: "Conseils juridiques en droit commercial et des sociétés. Révision des contrats conformément à la législation belge. Aide en droit administratif belge (immigration, visas Schengen, permis de travail).",
          image: "Capture-decran-2023-01-23-a-19.51.34",
          site: "http://www.dhaeyer.law/",
        },

        {
          secteur: "Services / Consultance",
          nom: "Katal Defense Security",
          profil:
            "Katal Defense Security est une société qui propose des formations tactiques réservées à des organismes ciblés tels que : forces armées, forces de l’ordre, protection de hauts cadres gouvernementaux, secteur privé, etc …",
          image: "banner-p-500",
          site: "https://www.katal-security.com",
        },
        // {
        //   secteur: "Services financiers",
        //   nom: "SFPIM",
        //   profil:
        //     "Fonds d'investissement destiné à accompgner les sociétés belges à l'étranger.",
        //   image: "sfpim",
        //   site: "https://www.sfpim-international.be",
        // },
        {
          secteur: "Services / Consultance",
          nom: "Campro",
          profil: "Vidéo-surveillance / securité/ alarme / solutions WiFi.",
          image: "campro",
          site: "https://www.campro.be",
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "VOKA",
          profil:
            "VITO est un organisme de recherche dans le domaine des technologies propres et du développement durable.",
          image: "voka",
          site: "https://www.voka.be/",
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "CBL-ACP",
          profil:
            "Disposant d’un réseau étendu d’experts et de représentants locaux, la Chambre assiste ses membres dans la réalisation de leurs projets et missions.",
          image: "cbl-acp",
          site: "https://www.cbl-acp.be",
        },
        {
          secteur: "Services / Consultance",
          nom: "Belgian Entreprenoires",
          profil:
            "Des opportunités pour l’entrepreneuriat afro-belge féminin de se faire connaitre et des opportunités pour le marché en général de découvrir de nouvelles marques, de nouveaux produits, de nouveaux visages.",
          image: "belgian_entreprenoires",
          site: "https://www.instagram.com/belgian_entreprenoires",
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "Observatoire des Sénégalais de la Diaspora (OSD)",
          profil:
            "Promotion des entrepreneurs économiques de la diaspora - Investissement - Formation - Consultance - Mise en relation des entrepreneurs et Investisseurs - Organisation de be-to-be entre entrepreneurs en Belgique et au Sénégal.",
          image: "ws",
          site: "http://observatoirediasporasenegal.com/",
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "BITIMREW PRESS GROUP - WABITIMREW.NET",
          profil: "PRESSE/COMMUNICATION.",
          image: "logo-rewFF",
          site: "https://www.instagram.com/belgian_entreprenoires",
        },
        // {
        //   secteur: "Fédération et chambre de commerce",
        //   nom: "BLUE CLUSTER",
        //   profil:
        //     "Soutient les entreprises de Flandres en vue de développer et de promouvoir les activités économiques en mer.",
        //   image: "blauwecluster",
        //   site: "https://www.blauwecluster.be",
        // },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "Cleantech Flanders",
          profil:
            "Promotion des technologies propres et assistance aux entreprises dans la mise en œuvre des technologies propres.",
          image: "cleantechflanders",
          site: "https://www.cleantechflanders.com",
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "CLUSTER H2O",
          profil:
            "Rassemble les acteurs du secteur de l'eau en Région Wallone.",
          image: "h2o-logo-hp_blanc_0",
          site: "https://clusters.wallonie.be/h2o/fr",
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "CLUSTER TECHNOLOGIE WALLONNE ENERGIE - ENVIRONNEMENT ET DEVELOPPEMENT DURABLE (TWEED)",
          profil:
            "Le Cluster s'attache à jouer un rôle majeur en matière de business dans les secteurs des énergies renouvelables et de l'optimisation énergétique.",
          image: "logo-tweed",
          site: "https://clusters.wallonie.be/tweed/fr",
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "PRESS CLUB BRUSSELS EUROPE",
          profil:
            "L'objectif du Club est de fournir un lieu de rencontre et d'affaires pour les journalistes professionnels.",
          image: "Press-Club-Brussels-Europe-Website-Header-2-Jan-2019",
          site: "https://www.pressclub.be/",
        },

        {
          secteur: "Fédération et chambre de commerce",
          nom: "UNIZO",
          profil: "Association d'entrepreneurs.",
          image: "logo_v2",
          site: "https://www.unizo.be/",
        },
        {
          secteur: "Fédération et chambre de commerce",
          nom: "VITO",
          profil:
            "VITO est un organisme de recherche dans le domaine des technologies propres et du développement durable.",
          image: "vito",
          site: "www.vito.be",
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
        .sort((a, b) => {
          if (a.nom < b.nom) {
            return -1;
          } else {
            return 1;
          }
        });
    },
    //   filterByCategory: function () {

    // }
  },
  methods: {

    showInscription() {
      this.$router.push("/inscription");
    },
    setSearchQuery(data) {
      this.searchQuery = data;
    },
    changeActive(e) {
      e.target.classList.add("checked");
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
        "Construction services / Infrastructure / Ingénierie"
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
  mounted() {
    setTimeout(() => {
      this.isLoading = false
    }, 1000)
  }

}
</script>
<style scoped>
.bdc {
  margin-top: 10%;
}

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

a {
  text-decoration: none;
}

/* label.checked {
  background-color: gray;
  color: black;
} */</style>