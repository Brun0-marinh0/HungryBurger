<template>
<Navbar/>
<div class="containerSite">
  <router-view/>
</div>

</template>

<script>
import Navbar from './components/Navbar.vue';
export default{
  components:{
    Navbar
  }
}
</script>

<style>
  :root {
    --white: #f5f5f5;
    --full_white:#ffffff;
    --red:#EE5157;
    --black: #222222;
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
  /* width */
  ::-webkit-scrollbar {
    width: 5px;
  }
  ::-webkit-scrollbar-thumb {
    background: var(--red); 
    border-radius: 10px;
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
