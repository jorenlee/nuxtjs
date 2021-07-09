<template>
     <div class="container">
          <div>
               <!-- <Logo /> -->
               <img :src="planet.image" alt="" />
               <h1 class="title">
                    {{ planet.title  }}
               </h1>
               <!-- <pre>{{ $data }}</pre> -->
               <!-- <NuxtLink to="/about">About</NuxtLink> -->
               <PlanetsList />
          </div>
     </div>
</template>

<script> 
     export default {
          transition: 'bounce',
          head() {
               return {
                    title: this.planet.title,
                    meta: [
                         {
                              hid: 'description',
                              name: 'description',
                              content: this.planet.description,
                         },
                    ],
               }
          },
          async asyncData({ params }) {
               const planet = await fetch(`https://api.nuxtjs.dev/planets/${params.slug}`).then((res) => {
                    if(res.ok) {
                         return res.json()
                    }
                    throw new Error(res.status)
               })
               return { planet }
          },
     }
</script>

<style>
     img {
          height: 80px;
          width: auto;
          object-fit: cover;
     }
</style>