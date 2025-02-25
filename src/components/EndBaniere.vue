<template>
    <div class="endbanner">
        <button @click="scrollToLeft" class="scroll-button">
            D.C.
        </button>
        <div class="endbanner-background">
            <img src="@/assets/banner/porte.svg" alt="fin de mesure">
        </div>
    </div>  
</template>

<script>
export default {
    methods: {
    scrollToLeft() {
        window.scrollTo({ left: 0, behavior: "smooth" });
    }
    }
};
</script>

<style lang="scss" scoped>

.endbanner{
    position: relative;
    width: 200px !important; 
    height: 100vh;
    box-sizing: border-box; 

    .scroll-button{
        position: absolute;
        top: 20px;
        right: 90px;
        background-color: transparent;
        color: #292929;
        border: none;
        cursor: pointer;
        font-size: 2em;
        font-weight: bold;
    }
    .endbanner-background{
        width: 100%;  /* Pour que l'image occupe toute la largeur de l'élément parent */
        max-width: 200px; /* Ajouté pour limiter la largeur de l'image à 200px */
        height: 100%;
        background: url('/src/assets/banner/paper.jpg') no-repeat center center;
        background-size: cover;
        display: flex;
        align-items: center;
        justify-content: center;
        overflow: hidden;
        box-shadow: -10px 0px 15px rgba(0, 0, 0, 0.2);
        img{
            height: 125%;
            position: absolute;
            left: 0;
            object-fit: cover;
            position: static;
        }
    }
}

</style>