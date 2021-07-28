<template>
    <div class="popup">
        <div class="card">
            <slot/>
            <button class="popup-close" @click="TogglePopup()">
                Close Popup
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
        display: block;
        text-align: center;
        width: 40rem;
        max-width: 40rem;
        height: 20rem;
        background: var(--white);

        box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
    }

</style>