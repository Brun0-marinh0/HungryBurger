<template>
    <div class="popup">
        <div class="card">
            <slot/>
            <button class="popup-close" @click="TogglePopup()">
                Cancelar
            </button>
         </div>
    </div>
</template>

<script>
export default {
    props:['TogglePopup']
}
</script>
<style scoped>
    .popup{
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
        color: var(--red);
        display: block;
        text-align: center;
        padding: 2rem;
        width: 30rem;
        max-width: 40rem;
        height: 15rem;
        border-radius: .8rem;
        background: var(--white);
        box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
    }
    button{
        border: none;
        background: var(--red);
        color: var(--white);
        padding: .3rem .8rem;
        border-radius: 1rem;
        width: 150px;
    }
    

</style>