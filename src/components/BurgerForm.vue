<template>
    <div class="message">
      <Message :msg="msg" v-show="msg" />  
    </div>
    
    <div class="containerMake">
        <div class="image_hungryBurger">
            <img :src="logoNome" :alt="alt" id="logoNome">
        </div>

        <div class="form">
            <div class="head__form">
                <h1>Crie o seu hámburguer</h1>
            </div>
            <form id="burger-form" @submit="createBurger">
                
                <div class="labelForm">
                    <label for="nome"> Nome do cliente</label><br>
                    <input type="text" id="nome" name="nome" v-model="nome" placeholder="Digite o seu nome">
                </div>

                <div class="labelForm">
                    <label for="bread">Escolha o Pão:</label><br>
                    <select name="pao" id="pao" v-model="pao">
                        <option value="">Selecione o seu pão</option>
                        <option v-for="pao in paes" :key="pao.id" :value="pao.tipo">
                            {{ pao.tipo}}
                        </option>
                    </select>
                </div>

                <div class="labelForm">
                    <label for="carne"> Escolha a carne do seu Burger:</label><br>
                    <select name="carne" id="carne" v-model="carne">
                        <option value="">Selecione o tipo de carne</option>
                        <option v-for="carne in carnes" :key="carne.id" :value="carne.tipo">
                            {{ carne.tipo}}
                        </option>
                    </select>
                </div>

                <div>
                    <label for="opcionais">Selecione os opcionais:</label>
                    <div class="checkbox-container" v-for="opcional in opcionaisdata" :key="opcional.id">
                        <input type="checkbox" name="opcionais" id="opcionais" v-model="opcionais" :value="opcional.tipo">
                        <span>{{opcional.tipo}}</span>
                    </div>
                </div>
                <div class="input-container">
                    <input type="submit" class="submit-bnt" value="Criar meu Burger">
                </div>
            </form>
        </div>
    </div>
</template>
<script>

import Message from './Message.vue';

export default {
    name: "BurgerForm",
    props:["logoNome", "alt"],

    data(){
        return{
            paes: null,
            carnes: null,
            opcionaisdata: null,
            nome: null,
            pao: null,
            carne: null,
            opcionais:[],
            msg: null
        }
    },
    methods:{
        async getIngredientes(){

            const req = await fetch("http://localhost:3000/ingredientes");
            const data = await req.json();

            this.paes = data.paes;
            this.carnes = data.carnes;
            this.opcionaisdata = data.opcionais;
        },
        async createBurger(e){
            
            e.preventDefault();

            const data = {
                nome: this.nome,
                carne: this.carne,
                pao: this.pao,
                opcionais: Array.from(this.opcionais),
                status:"Solicitados"
            }

            const dataJson = JSON.stringify(data);

            const req = await fetch("http://localhost:3000/burgers",{
                method: "POST",
                headers:{"Content-Type": "application/json"},
                body: dataJson
            });

            const res = await req.json();

            //colocar uma msg de sistema
            this.msg = `Olá ${this.nome} Pedido realizado com sucesso`;

            //limpar msg

            setTimeout(() => this.msg = "", 4000);


            //limpar os campos
            this.nome = "";
            this.carne = "";
            this.pao = "";
            this.opcionais = "";

        }
    },
    mounted(){
        this.getIngredientes()
    },
    components:{
        Message
    }
}
</script>

<style scoped>
    .message{
        height: 2rem;
        
    }
    .containerMake{
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: 2rem;
        min-height: 60vh;
    }
    .head__form{
        border-bottom: .3rem solid var(--red);
        text-align: center;
        margin-bottom: 1.5rem;
        padding: 0 0 1rem 0;
    }
    .image_hungryBurger{
        display: grid;
        height: 100%;
        background: var(--red);
        overflow: hidden;
    }
    .image_hungryBurger img{
        width: 100%;
        height: 100%;

        object-fit: cover;
        object-position: center right;
        display: block;

        filter: grayscale(20%);

    }
    .form{
        display: grid;
        justify-content: center;
        align-content: center;
        height: 100%;
    }
    .labelForm{
        margin-bottom: .4rem;
    }
    .labelForm label{
        text-transform: uppercase;
        font-weight:700;
        font-size: 1.3rem;
    }
    .labelForm input[type=text]{
        background: none;
        outline: none;
        border: none;

        width: 100%;
        padding: 1rem 0;

        border-bottom: 2px dashed var(--red);
        color: #37352F;
        

        text-transform: capitalize;
        font-weight:700;
        font-size: 1.5rem;
    }
    .labelForm select{
        width: 100%;
        text-transform: capitalize;
        font-weight:700;
        font-size: 1rem;
        color: #37352F;
    }

    .labelForm option{
        color: var(--black);
        background: var(--white);
    }
    .input-container input{
        background: var(--red);
        color: var(--white);

        width: 100%;
        padding: 1rem;
        text-transform: uppercase;
        font-weight: 800;

        border: none;
    }

    .input-container input:hover{

        font-weight: 700;
        font-size: 1rem;
    }
    .image_hungryBurger img{
        width: 100%;
    }

     @media only screen and (max-width: 768px) {

        .containerMake{
           grid-template-columns: 1fr;
           grid-template-rows: .3fr 1fr;
        }
        .image_hungryBurger img{
            height: 100%;
        }
     }

</style>