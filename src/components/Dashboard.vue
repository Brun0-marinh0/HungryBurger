<template>
    <div>
        <div class="tabelas">
            <div class="lista_pedidos">
                <h2>Gerenciador de pedidos</h2>
                <div class="scrollTabela">
                    <table class="table table-striped">
                        <thead>
                            <tr>
                                <th scope="col">Pedidos</th>
                                <th scope="col">Clientes</th>
                                <th scope="col">teste</th>
                                <th scope="col">Staus</th>
                                <th scope="col">Delete</th>
                            </tr>
                        </thead>
                            <tbody v-for="burger in burgers" :key="burger.id">
                            <tr @click = "amostra(burger.id,burger.nome,burger.pao,burger.carne)">
                                    <th scope="row">{{burger.id}}</th>
                                    <td>{{burger.nome}}</td>

                                    <td>
                                        <li v-for="(opcional, index) in burger.opcionais" :key="index">
                                            {{opcional}}
                                        </li>
                                    </td>

                                    <td>
                                        <select name="status" class="status">
                                            <option v-for="s in status" :key="s.id" value="s.tipo" :selected="burger.status == s.tipo">
                                                {{s.tipo}}
                                            </option>
                                        </select>
                                    </td>

                                    <td><button>excluir</button></td>
                                </tr>
                            </tbody>
                    </table>
                </div>

            </div>

            <div class="pedido">


                <div class="nomeCliente">
                    <input id="nome" value="" disabled>
                </div>
                
                <div class="tipo">
                    <input id="pao" value="" disabled>
                </div>

                <div class="tipo">
                    <input id="carne" value="" disabled>
                </div>
                
                
            </div>
        </div>
    </div>
</template>

<script>


export default {
    name: "Dashboard",
    data(){
        return{
            burgers: null,
            burger_id: null,
             testes : null,
            status: []
        }
    },
    methods: {
        amostra: function (id,nome,pao,carne){

        
        document.getElementById('nome').value = nome;
        document.getElementById('pao').value = pao;
        document.getElementById('carne').value = carne;
        
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
        }
    },
    mounted(){
       this.getPedidos();
      
    }
}
</script>

<style  scoped>
    .tabelas{
        display: grid;
        grid-template-columns: 1fr .5fr;
        grid-template-rows: 1fr;
        grid-gap: 1rem;
    }
    .lista_pedidos, .pedido{
        height: 87vh;
        border-radius: .5rem;
        padding: 1rem;
    }
    .pedido{
        background: var(--full_white);
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

    /* responsive========================================== */
    @media only screen and (max-width: 600px) {
        .tabelas{
            grid-template-columns: 1fr;
            grid-template-rows: 1fr 1fr;
        }
    }
</style>