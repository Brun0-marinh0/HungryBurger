<template>
    <div>
            <Message :msg="msg" v-show="msg" /> 

        <div class="container">
            <h2>Gerenciador de pedidos</h2>
            <div class="tabelas">
                <div class="lista_pedidos">
                    <div class="scrollTabela">
                        <table class="table table-striped">
                            <thead>
                                <tr>
                                    <th scope="col">Pedidos</th>
                                    <th scope="col">Clientes</th>
                                    <th scope="col">Staus</th>
                                    <th scope="col">Delete</th>
                                </tr>
                            </thead>
                                <tbody v-for="burger in burgers" :key="burger.id">
                                <tr @click = "amostra(burger.id,burger.nome,burger.pao,burger.carne,burger.opcionais)">
                                        <th scope="row">{{burger.id}}</th>
                                        <td>{{burger.nome}}</td>

                                        <td>
                                            <select name="status" class="status" @change="updatedBurger($event, burger.id)">
                                                <option v-for="s in status" :key="s.id" :value="s.tipo" :selected="burger.status == s.tipo">
                                                    {{s.tipo}}
                                                </option>
                                            </select>
                                        </td>

                                        <td>
                                            <button @click="() => TogglePopup('buttonTrigger') ">Deletar</button>

                                            <PopupDelete v-if="popupTriggers.buttonTrigger" :TogglePopup="() => TogglePopup('buttonTrigger')">
                                                <h3 class="titulo_excluir">Deseja realmente <b>excluir?</b></h3>
                                                <button class="bnt_excluir" v-if="popupTriggers.buttonTrigger" :TogglePopup="() => TogglePopup('buttonTrigger')" @click="deleteBurger(burger.id)">Exclui</button>
                                            </PopupDelete>
                                        </td>
                                    </tr>
                                </tbody>
                        </table>
                    </div>

                </div>

                <div class="pedido">


                    <div class="nomeCliente">
                        <input  id="nome" value="" disabled>
                    </div>
                    
                    <div class="tipo">
                        <label for="pao">Pão</label>
                        <input id="pao" value="" disabled>
                    </div>

                    <div class="tipo">
                        <label for="carne">Carne</label>
                        <input id="carne" value="" disabled>
                    </div>

                    <div class="tipo">
                        <label for="opcionais">Opcionais</label>
                        <div id="opcionais"></div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { ref } from 'vue';
import Message from './Message.vue';
import PopupDelete from './PopupDelete.vue'

export default {
    name: "Dashboard",
    setup(){
        const popupTriggers = ref({
            buttonTrigger:false,
            timedTrigger: false
        });

        const TogglePopup = (trigger) => {
            popupTriggers.value[trigger] = !popupTriggers.value[trigger]
        }


        return{
            PopupDelete,
            popupTriggers,
            TogglePopup
        }
    },
    data(){
        return{
            burgers: null,
            burger_id: null,
            status: [],
            msg: null
        }
    },
    components:{
       Message,
       PopupDelete
    },
    methods: {
        amostra: function (id,nome,pao,carne,opcionais){

            document.getElementById('nome').value = nome;
            document.getElementById('pao').value = pao;
            document.getElementById('carne').value = carne;

        
            var myhtml = "";
            for(var i=0; i < opcionais.length;i++){

                myhtml = myhtml +"•"+ opcionais[i]+"<br>";
            }

            document.getElementById('opcionais').innerHTML = myhtml;

        },
        async getPedidos(){
            const req = await fetch("http://localhost:3000/burgers");

            const data = await req.json();

            this.burgers = data;

            //resgatar status
            this.getStatus();
        },
        async getStatus(){
            const req = await fetch("http://localhost:3000/status");

            const data = await req.json();

            this.status = data;
        },
        async deleteBurger(id){
            
            const req = await fetch(`http://localhost:3000/burgers/${id}`,{
                method: "DELETE"
            });

            const res = await req.json();

            //colocar uma msg de sistema
            this.msg = `Pedido removido com sucesso!`;

            //limpar msg
            setTimeout(() => this.msg = "", 4000);

            this.getPedidos();
        },
         async updatedBurger(event, id){
             const option = event.target.value;

             const dataJson = JSON.stringify({status: option});

            const req = await fetch(`http://localhost:3000/burgers/${id}`,{
                 method:"PATCH",
                 headers:{ "Content-Type": "application/json"},
                 body: dataJson
            });

            const res = await req.json();

            //colocar uma msg de sistema
            this.msg = `Pedido N°${res.id} foi atualizado para ${res.status}!`;

            //limpar msg
            setTimeout(() => this.msg = "", 4000);
         }
    },
    mounted(){
       this.getPedidos();
    }
}
</script>

<style  scoped>
    .container{
        min-height: 85vh;
    }
    .message_status{
        height: 2rem;
        background: black;
    }
    .tabelas{
        display: grid;
        grid-template-columns: 1fr .5fr;
        grid-template-rows: 1fr;
        grid-gap: 1rem;
    }
    .lista_pedidos, .pedido{
        height: 70vh;
        border-radius: .5rem;
    }
    .pedido{
        background: var(--full_white);
        padding: 1rem;
        box-shadow: rgba(0, 0, 0, 0.1) 0px 4px 12px;
    }
    .lista_pedidos h2{
        margin-bottom: 2rem;
    }
    tr{
        cursor: pointer;
    }
    td select{
        width: 100%;
    }
    .pedido{
        display: block;
    }
    .pedido input{
        border: none;
        background: none;
        width: 100%;
        color: var(--red);
        font-size: 1.3rem;
    }
    .nomeCliente input{
        font-size: 1.5rem;
        font-weight: bold;
        margin-bottom: 1.3rem;
    }
    .tipo{
        margin-bottom: 1.5rem;
    }
    .scrollTabela{
        overflow-y: scroll;
        height: 70vh;
    }
    button{
        border: none;
        background: var(--red);
        color: var(--white);
        padding: .3rem .8rem;
        border-radius: 1rem;
    }
    .bnt_excluir{
        background: #f89396;
        margin-right: 3rem;
        width: 150px;
    }
    .titulo_excluir{
        margin-bottom: 5rem;
    }
    label{
        color: var(--black);
    }

    /* responsive========================================== */
    @media only screen and (max-width: 768px) {
        .tabelas{
            grid-template-columns: 1fr;
            grid-template-rows: .5fr 1fr;
        }
        .lista_pedidos, .pedido{
            display: grid;
            height: auto;
            width: 100%;
        }
        .lista_pedidos{
            order: 1;
        }
        .scrollTabela{
            height: 50vh;
        }
        .pedido input{
            font-size: 1.2rem;
        }
    }
</style>