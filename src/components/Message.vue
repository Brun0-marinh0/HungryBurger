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

</style>
