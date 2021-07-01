<template>
     <div class="container">
          <!-- <more-fun/> -->
          <div>
               <Logo />
               <h1 class="title">
                    Nuxt Mission
               </h1>
               <!-- <button @click="showPlanets">
                    Show Planets
               </button>
               <div v-if="show">
                    <LazyPlanetsList />
               </div> -->
               <PlanetsList />   
          </div>
     </div>
</template>

<script>
     // import PlanetsList from '~/components/PlanetsList'
     // export default {
     //      components: {
     //           PlanetsList,
     //      },
     // }
     export default {
          data() {
               return {
                    show: false,
               }
          },
          methods: {
               showPlanets() {
                    this.show = true
               },
          },
     }
</script>

<style>
     ul {
          list-style-type: none;
          padding: 0;
     }
     .container {
          
     }
</style>