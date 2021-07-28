<template>
     <div class="w-full">
          <button @click="back()" class="ml-10">Back</button>
     </div>
</template>

<script>
     export default {
          data() {
               return {

               }
          },
          methods : {
               back() {
                    this.$router.push("/");
               }
          }
     }
</script>