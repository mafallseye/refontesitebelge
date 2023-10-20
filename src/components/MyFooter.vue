<template>
<div class="">
    <div class=" float-start " > 
        
        <div class="card" style="width: 18rem; border: none;">
  <div class="card-body">
    <!-- <h5 class="card-title">Card title</h5> -->
    <!-- <h6 class="card-subtitle mb-2 text-body-secondary">Card subtitle</h6> -->
    <p class="card-text">
        hub.brussel vise à promouvoir l'internationalisation de l'économie bruxelloise en assistant les entreprises bruxelloises sur les marchés étrangers</p>
  
  </div>
</div>
        </div>
<div class=" float-end" >
    <div class="card" style="width: 18rem; border: none;">
  <div class="card-body">
    <!-- <h5 class="card-title">Card title</h5> -->
    <!-- <h6 class="card-subtitle mb-2 text-body-secondary">Card subtitle</h6> -->
    <p class="card-text">
        Le service Economique et Commercial ne s'occupe pas de Visas</p>
  
  </div>
</div>
</div>
<footer class="bg-white   dark:bg-gray-800">
    <div class="w-full mx-auto max-w-screen-xl p-2 md:flex md:items-center md:justify-between">
      <span class="text-sm text-gray-500 sm:text-center dark:text-gray-400">
    </span>
    <!-- <ul class="flex flex-wrap items-center mt-3 text-sm font-medium text-gray-500 dark:text-gray-400 sm:mt-0"> -->
        <!-- <li>
            <a href="#" class="mr-4 hover:underline md:mr-6 ">About</a>
        </li>
        <li>
            <a href="#" class="mr-4 hover:underline md:mr-6">Privacy Policy</a>
        </li>
        <li>
            <a href="#" class="mr-4 hover:underline md:mr-6">Licensing</a>
        </li>
        <li>
            <a href="#" class="hover:underline">Contact</a>
        </li>
    </ul> -->
    </div>
</footer>
<button type="button" v-show="scY > 300"  @click="toTop" class=" fixed right-0 bottom-0 text-blue-700 border border-red-600 hover:bg-red-600 hover:text-white focus:ring-4 focus:outline-none focus:ring-red-300 font-medium rounded-full text-sm p-2.5 text-center inline-flex items-center dark:border-red-500 dark:text-red-500 dark:hover:text-white dark:focus:ring-red-800 dark:hover:bg-red -500">
    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="3.5"
                    stroke="currentColor" class="w-6 h-6 text-gray-900 hover:text-white">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M4.5 15.75l7.5-7.5 7.5 7.5" />
                </svg>
  <span class="sr-only">Icon description</span>
</button>
</div>

</template>
<script>
export default {
    data() {
        return {
            annee: new Date(),
            scTimer: 0,
        scY: 0,
        }
    },
  
        methods: {
      handleScroll: function () {
        if (this.scTimer) return;
        this.scTimer = setTimeout(() => {
          this.scY = window.scrollY;
          clearTimeout(this.scTimer);
          this.scTimer = 0;
        }, 100);
      },

      toTop: function () {
        window.scrollTo({
          top: 0,
          behavior: "smooth"
        });
      },
    },
        
    mounted() {
      window.addEventListener('scroll', this.handleScroll);
    }

}
</script>