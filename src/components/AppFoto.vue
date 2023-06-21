<template>
  <div class="container foto" v-bind:style="{ backgroundImage: 'url(' + foto + ')' }">
  </div>
</template>

<script>

export default {
  name: "AppFoto.vue",
  props:{
    foto: String
  }
}
</script>

<style scoped>
 .foto {
   width: 200px;
   height: 200px;
   background-size: cover;
   border-radius: 50%;
 }
</style>
