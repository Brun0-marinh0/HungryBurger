<template>
   <div class="mainBanner">
       <div class="mainBanner__inform">
           <div class="informacao">
               <h1>Crie o seu hambúrguer<br> que satisfarça a sua<br>fome!</h1>

               <router-link class="btnMake" to="/MakeBurger">CRIAR</router-link>
           </div>
       </div>
       <div class="mainBanner__illustration">
           <div class="illustration">
               <svg class="emote" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 340.7 349.7">
                    <title>emote</title>
                    <g id="emote">
                        <g id="cabeça">
                            <path class="cls-1" d="M803,227c0-8,5-17,5-17-2,14,8,36,8,36l-4,4C804,244,803,227,803,227Z" transform="translate(-725.8 -116.6)"/>
                            <g>
                            <path class="cls-2" d="M831.4,260.7c-16.8-4.4-27.8-19.9-28.1-37.1a40.3,40.3,0,0,0-29.7,29.3c-5.7,21.4,6.3,43.2,26.7,48.6s41.6-7.6,47.3-29.1A45,45,0,0,0,849,261,36.2,36.2,0,0,1,831.4,260.7Z" transform="translate(-725.8 -116.6)"/>
                            <path class="cls-3" d="M1004.5,297.7a105.1,105.1,0,0,0-199.6-31.6c-35.2,8.1-63.9,32.3-73.4,66.3-14.6,52.3,21.5,108,80.6,124.5l4,1.1H816c80.2,22.4,163.4-22.7,185.5-101.9C1005.5,341.8,1007.4,318.7,1004.5,297.7Z" transform="translate(-725.8 -116.6)"/>
                            </g>
                        </g>
                        <g id="cabelo">
                            <g>
                            <g>
                                <path class="cls-3" d="M949.5,148.7c15.7-16.2,24.7-24.4,29.7-28.5a5,5,0,0,1,8,2.5,193.9,193.9,0,0,0,16.5,41.9,93,93,0,0,0,32.7,35.2,72.4,72.4,0,0,0,23.7,9.9,4.8,4.8,0,0,1,2.8,7.8,212.3,212.3,0,0,1-17.1,18.1Z" transform="translate(-725.8 -116.6)"/>
                                <path class="cls-3" d="M1045.2,247.3l-21.4,24.6L910.7,173.7,932.2,149a10,10,0,0,1,11.9-2.4c53.9,27.4,89.7,72,101.7,88.5A9.9,9.9,0,0,1,1045.2,247.3Z" transform="translate(-725.8 -116.6)"/>
                            </g>
                            <path class="cls-2" d="M911.2,168.4a132,132,0,0,0-78.5,13.8c-13.3,4.8-23.6,17.1-25.7,32.7-3,21.9,11.6,42,32.5,44.8h.4c35.8,5.7,43.9,17.9,43.9,17.9-4.1-23.6,3.9-34.5,3.9-34.5,3.1,19.2,42.8,19.5,42.8,19.5,25.7,3.4,31,16.7,30.7,27.8a33.3,33.3,0,0,1-8.4,21.1c-27.8,31.4-2.4,62.9-2.4,62.9,4.8-25.3,18.2-34,29-36.8a4,4,0,0,1,5,4.1c-.2,2.2-.3,4.4-.4,5.2a177.4,177.4,0,0,1-4.1,19.5l31.9,12.3a149.2,149.2,0,0,0,15.8-49.7C1038.3,250.5,986.1,178.5,911.2,168.4Z" transform="translate(-725.8 -116.6)"/>
                            </g>
                        </g>
                        <g id="rosto">
                            <g id="orelha">
                            <path class="cls-3" d="M973.2,359.9a24.3,24.3,0,1,1-4.1,25" transform="translate(-725.8 -116.6)"/>
                            <g>
                                <line class="cls-4" x1="260.6" y1="266.8" x2="272.6" y2="254.8"/>
                                <line class="cls-4" x1="272.6" y1="266.8" x2="260.6" y2="254.8"/>
                            </g>
                            </g>
                            <g>
                            <g id="olhoFechado" data-name="&lt;olhoFechado&gt;">
                                <path class="cls-4" d="M879.5,317.5c23.7-8.7,28.6,13.3,29.2,17" transform="translate(-725.8 -116.6)"/>
                                <path class="cls-2" d="M842.5,269.6a8.2,8.2,0,0,0-4.5-1h0c-8.2.4-16.3,9.3-22.1,17.7l4.5,6.9-9,.5h0a10.9,10.9,0,0,0-.8,1.5,132.8,132.8,0,0,0-7.1,17.2h.1a8.4,8.4,0,0,0,15.4,6.7,5.2,5.2,0,0,0,.6-1.3h0a59.3,59.3,0,0,1,4.7-11.8,60.3,60.3,0,0,1,18.8-21.7h0a9.2,9.2,0,0,0,3-3.2A8.5,8.5,0,0,0,842.5,269.6Z" transform="translate(-725.8 -116.6)"/>
                            </g>
                            <g id="olhosAberto" data-name="&lt;olhosAberto&gt;">
                                <path class="cls-2" d="M842.5,269.6a8.2,8.2,0,0,0-4.5-1h0c-8.2.4-16.3,9.3-22.1,17.7l4.5,6.9-9,.5h0a10.9,10.9,0,0,0-.8,1.5,132.8,132.8,0,0,0-7.1,17.2h.1a8.4,8.4,0,0,0,15.4,6.7,5.2,5.2,0,0,0,.6-1.3h0a59.3,59.3,0,0,1,4.7-11.8,60.3,60.3,0,0,1,18.8-21.7h0a9.2,9.2,0,0,0,3-3.2A8.5,8.5,0,0,0,842.5,269.6Z" transform="translate(-725.8 -116.6)"/>
                                <path class="cls-2" d="M921.5,289.4a10.3,10.3,0,0,0-5.4-1.1h0c-9.8.5-19.7,11.2-26.6,21.4l5.4,8.3-10.8.6H884l-.9,1.8a153.5,153.5,0,0,0-8.6,20.7h.1a10.2,10.2,0,0,0,18.7,8,4.7,4.7,0,0,0,.6-1.5h.1a69.6,69.6,0,0,1,5.6-14.3,74.2,74.2,0,0,1,22.7-26.2h0a9.7,9.7,0,0,0,3.6-3.9A10.2,10.2,0,0,0,921.5,289.4Z" transform="translate(-725.8 -116.6)"/>
                            </g>
                            <path class="cls-3" d="M848.9,350a18.4,18.4,0,0,1-15.5,4.9c-9.6-1.3-16.5-9-15.4-17.3s9.8-13.9,19.4-12.6a19.1,19.1,0,0,1,10.3,4.6" transform="translate(-725.8 -116.6)"/>
                            <g>
                                <g>
                                <path class="cls-4" d="M908.2,432.4a32.9,32.9,0,0,1-24.8-11.7,33.4,33.4,0,0,1,3.7-47.1" transform="translate(-725.8 -116.6)"/>
                                <path class="cls-2" d="M878.4,412.1a39.2,39.2,0,0,1-1.8-22.4c-19.4,2.4-55.5,1.7-81.1-30a17.5,17.5,0,0,0-26.6-1.3l-.9,1c-9.3,10.4-9.7,26.5-1.6,37.5,15.2,20.4,52.1,53.4,123.7,30.6A35.2,35.2,0,0,1,878.4,412.1Zm-17.1,17.4c-55.4,4.9-76.5-20.2-81.9-25.4a21.1,21.1,0,0,1,9.6-9.3c7.8-3.6,18.1-3,30.7,1.7a61.5,61.5,0,0,0-18.2,8.3,2.2,2.2,0,0,0-.5,2.9,1.9,1.9,0,0,0,2.8.5c.2-.1,19.8-13.7,38.5-7.8,11,3.5,19.6,12.8,25.7,27.8A30.5,30.5,0,0,1,861.3,429.5Z" transform="translate(-725.8 -116.6)"/>
                                </g>
                                <g>
                                <circle class="cls-2" cx="168.3" cy="290.5" r="4.1"/>
                                <circle class="cls-2" cx="181" cy="274.4" r="4.1"/>
                                <circle class="cls-2" cx="191.6" cy="292.1" r="4.1"/>
                                </g>
                                <g>
                                <circle class="cls-2" cx="27.7" cy="226.1" r="4.1"/>
                                <circle class="cls-2" cx="29.6" cy="205.6" r="4.1"/>
                                <circle class="cls-2" cx="48.1" cy="214.7" r="4.1"/>
                                </g>
                            </g>
                            </g>
                        </g>
                    </g>
               </svg>
           </div>
           <div class="logoNome">
               <img :src="logoNome" :alt="alt" id="logoNome">
           </div>
       </div>
   </div>
</template>
<script>
    export default{
        name:"Banner",
        props:["logoNome", "alt"]
    }
</script>
<style scoped>

    .cls-1, .cls-3 {
    fill: #f5f5f5;
    }
    .cls-2 {
    fill: #ee5157;
    }
    .cls-3, .cls-4 {
    stroke: #ee5157;
    stroke-linecap: round;
    stroke-miterlimit: 10;
    stroke-width: 5px;
    }
    .cls-4 {
    fill: none;
    }

    .mainBanner{
        width: 80%;
        display: grid;
        grid-gap: 1rem;
        grid-template-columns: 1fr .5fr;
        margin: 0 auto;
    }
    .emote{
        width: 100%;
    }
    .mainBanner__illustration{
        justify-content: center;
        display: grid;
        grid-template-rows: 1fr .4fr;
    }
    .illustration{
        width: 100%;
        display: grid;
        justify-content: center;
        align-items: center;
    }
    .mainBanner__inform{
        display: grid;
        margin: auto;
    }
    .informacao h1{
        font-size: 3.6vw; 
        margin-bottom: 2rem; 
    }

    .informacao .btnMake{
        text-decoration: none;
        color: var(--white);
        background: var(--red);
        padding: 1rem 2rem;
        border-radius: .5rem;
        font-size: 1.5rem;
        font-weight: bold;

        transition: .3s;
    }
    .informacao .btnMake:hover{
        padding: 1.5rem 2.5rem;
    }
    .logoNome{
        display: grid;
       padding: 1rem;
    }
    /* animation============================ */
    .emote{
        animation: emote 3s infinite linear alternate;
        transform-origin:center;
        transform-box: fill-box;
    }
    @keyframes emote{
        0% {
            transform: rotateZ(0deg);
        }
        25% {
            transform: rotateZ(0deg);
        }
        50% {
            transform: rotateZ(0deg);
        }
        100% {
            
            transform: rotateZ(3deg);
        }
    }
     #olhosAberto{
        animation: olhosAberto 3s infinite cubic-bezier(0.68, -0.28, 0.35, 1.58) alternate;
        transform-origin: center;
        transform-box: fill-box;
        
    }
    @keyframes olhosAberto{
        0% {
            opacity: 1;
        }

        25% {
            opacity: 1;
        }

        50% {
            opacity: 1;
        }

        100% {
            
            opacity: 0;
        }
    } 
    #olhoFechado{
        animation: olhoFechado 3s infinite cubic-bezier(0.68, -0.28, 0.35, 1.58) alternate;
        transform-origin: center;
        transform-box: fill-box;
    }
    @keyframes olhoFechado{
        0% {
            opacity: 0;
        }
        25% {
            opacity: 0;
        }
        50% {
            opacity: 0;
        }
        100% {
            
            opacity: 1;
        }
    }
    /* responsive================================================= */
    @media only screen and (max-width: 600px) {
    .mainBanner{
        grid-template-columns: 1fr;
        grid-template-rows: 1fr .5fr;
    }
    .mainBanner__inform{
        order: 1;
        border: none;
        margin: 0;
    }
    .informacao h1{
        font-size: 6vw;
    }
    .informacao{
        text-align: center;
    }
    .mainBanner{
        width: 100%;
    }
    .emote{
        width: 50%;
        margin: 0 auto;
    }
  }
</style>
