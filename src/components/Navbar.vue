<template>
    <div class="navbar-site" id="nav">
        <router-link class="links" to="/">Home</router-link>  
        <router-link class="links" to="/pedidos">Pedidos</router-link>
    </div>
</template>
<script>
export default{
    name: "Navbar"
}
</script>
<style scoped>
    .navbar-site{
        padding: 1rem;
    }
    .links{
        text-decoration: none;
        font-weight: bold;
        color: var(--red);
        padding: .2rem .7rem;
        border-radius: 1rem;
        margin-right: 1rem;
        transition: .2s;
    }
    .links:hover,.links:focus{
        color: var(--white);
        background-color: var(--red);
    }
</style>