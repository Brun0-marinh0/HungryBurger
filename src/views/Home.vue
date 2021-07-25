<template>
  <div class="home">
    <Banner :logoNome="logoNome_src" :alt="app_name"/>
    <Main/>
    <BestBurger/>
  </div>
</template>

<script>
  import Banner from "../components/Banner.vue"
  import Main from "../components/Main.vue"
  import BestBurger from "../components/BestBurger.vue"

  export default{
    name: "Home",
    components:{
      Banner,
      Main,
      BestBurger
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