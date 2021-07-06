<template>
<div class="container">
  <Navbar/>
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
    --red:#EE5157;
    --black: #22222;
  }
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body{
    background: var(--white);
    font-family: sans-serif;
    margin: .6rem;
    color: var(--red);
  }

  .container{
    border: .3rem solid var(--red);
    width: 100%;
    min-height: 100vh;
    padding: 2rem;
  }

  @media only screen and (max-width: 768px) {
    .container{
       padding: .5rem;
    }
  }
</style>
