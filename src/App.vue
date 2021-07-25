<template>
<Navbar/>
<div class="containerSite">
  <router-view/>
</div>
<Footer :burgerBoy="img_src" :alt="app_name"/>
</template>
<script>
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';
export default{
  components:{
    Navbar,
    Footer
  },
  data(){
    return{
      img_src: "/img/burgerBoy/burgerBoy-dark.svg",
      alt: "hungryBurger"
    }
  }
}
</script>

<style>
  :root {
    --white: #f5f5f5;
    --full_white:#ffffff;
    --red:#EE5157;
    --black: #222222;
    --footer:#343A40;
  }

  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@200;500;700&display=swap');

  body{
    background: var(--white);
    font-family: 'Poppins', sans-serif;
    color: var(--red);
  }
  p,h1,h2,h3{
    margin: 0px;
  }
  
  /* width */
  ::-webkit-scrollbar {
    width: 5px;
  }
  ::-webkit-scrollbar-thumb {
    background: var(--red); 
    border-radius: 10px;
  }
  /* Track */
  ::-webkit-scrollbar-track {
   background: rgba(128, 128, 128, 0.575);

  }

  .containerSite{
    width: 100%;
    padding: 1rem;
  }


  @media only screen and (max-width: 768px) {
    .container{
       padding: .5rem;
    }
  }
</style>
