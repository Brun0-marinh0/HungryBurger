<template>
    <div class="navbar" id="nav">
        <router-link class="links" to="/">
            Home
        </router-link>  
    </div>
</template>
<script>
export default{
    name: "Navbar"
}
</script>
<style scoped>
    .navbar{
        padding: 1rem;
    }
    .links{
        text-decoration: none;
        font-weight: bold;
        color: var(--red);
        padding: .2rem .7rem;
        border-radius: 1rem;
        transition: .2s;
    }
    .links:hover{
        color: var(--white);
        background-color: var(--red);
    }
</style>