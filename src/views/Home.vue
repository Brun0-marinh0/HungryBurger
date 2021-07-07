<template>
  <div class="home">
    <Banner :logoNome="logoNome_src" :alt="app_name"/>
    <Main/>
  </div>
</template>

<script>
  import Banner from "../components/Banner.vue"
  import Main from "../components/Main.vue"

  export default{
    name: "Home",
    components:{
      Banner,
      Main
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