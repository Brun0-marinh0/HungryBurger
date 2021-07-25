<template>
    <footer>
        <div class="flex__footer">
            <div class="links">
                <h3>Contato</h3>
                <div class="contatos">
                    <a href="https://www.behance.net/BrunoCMarinho" target="_blank" rel="noopener noreferrer">
                        <i class="fab fa-behance-square"></i>
                    </a>
                    <a href="https://github.com/Brun0-marinh0" target="_blank" rel="noopener noreferrer">
                        <i class="fab fa-github-square"></i>
                    </a>
                    <a href="https://www.linkedin.com/in/bruno-cmarinho/" target="_blank" rel="noopener noreferrer">
                        <i class="fab fa-linkedin"></i>
                    </a>
                    <a href="https://www.instagram.com/brun0.caldas/" target="_blank" rel="noopener noreferrer">
                        <i class="fab fa-instagram-square"></i>
                    </a>
                </div>
                <p>&copy Bruno Marinho</p>
            </div>
            
            <img :src="burgerBoy" :alt="alt" id="burgerBoy">
            
        </div>
        
    </footer>
</template>

<script>
export default {
    name:"Fotter",
    props:["burgerBoy", "alt"]
}
</script>

<style scoped>
    footer{
        background: var(--footer);
        color: var(--white);
        width: 100%;
        height: 18.5rem;
        overflow: hidden;
    }
    .flex__footer{
       display: flex;
       overflow: hidden;
    }
    .flex__footer img{
        position: relative;
        width: 40vw;
        top: -16vw;
        right: -70vw;
        z-index: 0;
       
    }
    .links{
        padding: 5rem;
        position: absolute;
        z-index: 99;
        width: 100%;
        align-items: center;
    }
    .links .contatos{
        display: flex;
        justify-content: center;
    }
    .links h3, .links p{
        text-align: center;
    }
    .links a{
        color: var(--white);
        margin: 0 1rem;
        font-size: 3rem;
        transition: .2s;
    }
    .links a:hover{
        color: var(--red);
    }
    .copy{
        background: var(--black);
    }
    @media only screen and (max-width: 600px) {
        .flex__footer img{
            width: 90vw;
            right: -40vw;
        }
    }
</style>