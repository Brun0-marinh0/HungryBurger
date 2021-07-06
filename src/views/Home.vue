<template>
  <div class="home">
    <Banner :logoNome="logoNome_src" :alt="app_name"/>
    <h1>home</h1>
  </div>
</template>

<script>
  import Banner from "../components/Banner.vue"

  export default{
    name: "Home",
    components:{
      Banner
    },
    data(){
      return{
        logoNome_src: "/img/nome.svg",
        alt: "HungryBurger"
      }
    }
  }
</script>

<style scoped>

</style>