<template>
  <div class="containerForm">
    <BurgerForm :logoNome="imagem_src" :alt="app_name" />
  </div>
</template>

<script>
  import BurgerForm from '../components/BurgerForm.vue'
  export default{
    name: "MakeBurger",
    components:{
      BurgerForm
    },
    data(){
      return{
       imagem_src: "/img/burger.jpg",
        alt: "HungryBurger"
      }
    }
  }
</script>

<style scoped>
</style>