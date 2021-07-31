<template>
    <div class="message__container">
        <p>{{msg}}</p>
    </div>
</template>
<script>
    export default ({
        name: "Message",
        props:{
            msg: String
        }
    })
</script>
<style scoped>
.message__container{
    position: fixed;
    top: 0;
    width: 100%;
    padding: 1rem;
    font-weight: 700;


    background: var(--red);
    color: var(--white);
}
</style>
