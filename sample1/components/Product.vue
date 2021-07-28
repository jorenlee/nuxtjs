<template>
  <div>
    <Header class="lg:mb-10 mb-5"/>
    <div class="w-11/12 mx-auto mt-16">
      <div class="font-bold md:flex justify-between">
        <div class="text-2xl lg:ml-2 text-center mb-10">BAGS</div>
        <div class="md:flex md:ml-12">
          <div class="border rounded-md h-9 flex w-full">
            <input
              type="text"
              placeholder="Search" 
              class="search pl-3 py-1 w-full focus:outline-none"
              id="search"
              name="search"
              v-model="searchQuery"/>
            <i class="fas fa-search px-2 text-gray-300 py-2"></i>
          </div>
        </div>
      </div>
      <div class="flex mx-auto flex-wrap lg:justify-left lg:pl-24 lg:w-full md:w-11/12 mb-5">
        <a 
          :href="product.slug"
          v-for="product in resultQuery || products" :key="product.slug" class="inline-block lg:mx-5 md:mx-12 mx-auto w-56 my-5 hover:shadow p-6">
          <img
            :src="require(`~/assets/${product.image_url}`)"
            alt=""
            class="lg:h-40 w-44 h-44 mb-1 mx-auto object-cover"
          />
          <div>
            <div class="text-sm font-bold">
              {{ product.name }}
            </div>
            <div class="text-xs">
              {{ product.price }}
            </div>
          </div>
        </a>
      </div>
    </div>
  </div>
</template>

<script lang="js">
import { mapState } from "vuex";
  export default {
    data() {
      return {
        searchQuery: '',
        products: [
          {
            id: 1,
            name: "Bag 1",
            image_url: 'product1.jpg',
            price: 1000.00,
            slug: 'bag-1'
          },
          {
            id: 2,
            name: "Bag 2",
            image_url: 'product2.jpg',
            price: 1500.00,
            slug: 'bag-2'
          },
          {
            id: 3,
            name: "Bag 3",
            image_url: 'product3.jpg',
            price: 2000.00,
            slug: 'bag-3'
          },
          {
            id: 4,
            name: "Bag 4",
            image_url: 'product4.jpg',
            price: 5000.00,
            slug: 'bag-4'
          },
          {
            id: 5,
            name: "Bag 5",
            image_url: 'product5.jpg',
            price: 9000.00,
            slug: 'bag-5'
          },
        ]
      }
    },
    computed: {
      resultQuery(){
        if(this.searchQuery){
          return this.products.filter((product)=>{
            return (product.name + ' ' + product.price).toLowerCase().includes(this.searchQuery.toLowerCase())
          })
        }
      }
    }
  }
</script>