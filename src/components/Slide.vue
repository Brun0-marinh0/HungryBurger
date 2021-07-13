
<template>

    <div id="carouselExampleFade" class="carousel slide carousel-fade" data-bs-ride="carousel">
        
        <div class="carousel-inner">

            <div class="carousel-item active">
                <img class="d-block w-100" :src="slide1" :alt="alt" id="slide1">
            </div>

            <div class="carousel-item">
                <img class="d-block w-100" :src="slide2" :alt="alt" id="slide2">
            </div>

            <div class="carousel-item">
                <img class="d-block w-100" :src="slide3" :alt="alt" id="slide3">
            </div>

        </div>

        <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleFade" data-bs-slide="prev">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Previous</span>
        </button>

        <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleFade" data-bs-slide="next">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Next</span>
        </button>
    </div>

</template>
<script>
    export default ({
        name: "Slide",
        props:["slide1","slide2","slide3", "alt"]
    });
</script>
<style scoped>
    #carouselExampleFade{
        height: 100%;
    }

    .carousel-item img{
        height: 38vw;
        width: 100%;
        object-fit: cover;
        object-position: center top;
        display: block;
    }
</style>
