<template>
    <div class="sobre">
        <div class="melhor">
            <h2>O melhor hamburger é o que você faz.</h2>
            <p id="paragrafo">Mais de 400 mil possibilidades de satisfazer a sua fome!</p>
        </div>
        
        <div class="descricoes">
            <div class="descricao">
                    <div class="qualidade__ilustracao">
                        <img src="/img/pao.svg" alt="">
                    </div>
                    <div class="qualidade__texto">
                        <p>Pão quentinho e fofinho!</p>
                    </div>
            </div>
            <div class="descricao">
                    <div class="qualidade__ilustracao">
                            <img src="/img/carne.svg" alt="">
                    </div>
                    <div class="qualidade__texto">
                        <p>Carne da melhor qualidade!</p>
                    </div>
            </div>
            <div class="descricao">
                    <div class="qualidade__ilustracao">
                        <img src="/img/alface.svg" alt="">
                    </div>
                    <div class="qualidade__texto">
                        <p>Igredientes frescos!</p>
                    </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "BestBurger"
}
</script>

<style scoped>
    .melhor h2{
        font-size: 3vw;
        font-weight: 600;
    }
    .melhor p{
        font-size: 1.5vw;
    }
    .sobre{
        margin-top: 3rem;
        text-align: center;
    }
    #paragrafo{
        color: var(--black);
    }
    .descricoes{
        margin: 7rem 0;
        display: grid;
        justify-content: center;
        grid-gap: 4rem;
    }
    .descricao{
        max-width: 40rem;
        display: grid;
        grid-template-columns:  7rem 1fr;
        grid-template-rows: 7rem;
        grid-gap: 1.5rem;
    }
    .qualidade__ilustracao{
        width: 100%;
        height: 100%;
        padding: .8rem;
        display: grid;
        grid-template: 1fr/1fr;
        align-items: center;
        border-radius: .5rem;
        background: var(--red);

    }
    .qualidade__ilustracao img{
        width: 100%;
        align-items: center;
    }
    .qualidade__texto{
        display: grid;
        align-content: center;
        text-align: start;
    }
    .qualidade__texto p{
        font-size: 1.5rem;
        font-weight: bold;
    }
    @media only screen and (max-width: 768px) {
        .melhor h2{
            font-size: 4.5vw;
        }
        .melhor p{
            font-size: 2.5vw;
        }
        .descricao{
            width: 100%;
        }
        
    }
</style>