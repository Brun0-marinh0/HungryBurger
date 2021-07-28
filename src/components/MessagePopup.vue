<template>
    <div class="message__container">
        <div class="card">
            <div class="texto">
                <h3>{{msg}}</h3>
            </div>
        </div>
    </div>
</template>
<script>
    export default ({
        name: "MessagePopup",
        props:{
            msg: String
        }
    })
</script>
<style scoped>
.message__container{
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: 99;
    background: rgba(0, 0, 0, 0.2);
    display: flex;
    align-items: center;
    justify-content: center;
}
.card{
    display: block;
    text-align: center;
    width: 40rem;
    max-width: 40rem;
    height: 20rem;
    background: var(--white);

    box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
}
.texto{
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100%;
}
.texto h3{
    font-size: 1.2rem;
    font-weight: bold;
}
</style>
