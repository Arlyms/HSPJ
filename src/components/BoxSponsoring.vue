<template>
    <div id="baniere">
        <div class="baniere-animation">
            <div class="logos">
                <img src="../assets/sponsors/departementNB.png" alt="logo du departement de la loire">
                <img src="../assets/sponsors/MairieNB.png" alt="logo de la mairie de saint priest en jarez">
                <img src="../assets/sponsors/mutueNB.png" alt="logo du credit mutuel">
                <img src="../assets/sponsors/TardyNB.png" alt="logo du cabinet tardy immobilier">
            </div>
            <!--Clone des logos pour une fluiditée du déroulement infinie-->
            <div class="logos">
                <img src="../assets/sponsors/departementNB.png" alt="logo du departement de la loire">
                <img src="../assets/sponsors/MairieNB.png" alt="logo de la mairie de saint priest en jarez">
                <img src="../assets/sponsors/mutueNB.png" alt="logo du credit mutuel">
                <img src="../assets/sponsors/TardyNB.png" alt="logo du cabinet tardy immobilier">
            </div>
            <div class="logos">
                <img src="../assets/sponsors/departementNB.png" alt="logo du departement de la loire">
                <img src="../assets/sponsors/MairieNB.png" alt="logo de la mairie de saint priest en jarez">
                <img src="../assets/sponsors/mutueNB.png" alt="logo du credit mutuel">
                <img src="../assets/sponsors/TardyNB.png" alt="logo du cabinet tardy immobilier">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:"Baniere",
}
</script>

<style lang="scss" scoped>

#baniere   {    

    margin: 0;
    padding: 0;
    box-sizing: border-box;
    background-color: rgb(255, 255, 255) ;

    }
    .baniere-animation{
        overflow: hidden;
        margin-bottom: 50px;
        padding: 15px 0;
        background-color: rgb(255, 255, 255);
        white-space: nowrap;
        position: relative;
        &::before,
        &::after {
                position: absolute;
                top: 0;
                width: 250px;
                height: 100%;
                content: "";
                z-index: 2;
        } 
        &::before{
            left: 0;
            background: linear-gradient(to left, rgb(255, 255, 255, 0), rgb(255, 255, 255));
        }
        &::after{
            right: 0;
            background: linear-gradient(to right, rgb(255, 255, 255, 0), rgb(255, 255, 255));
        }
        &:hover .logos{
            animation-play-state: paused;
        }
        .logos{
            display: inline-block;
            animation: slide 20s infinite linear;
            img{
                height: 70px;
                margin: 0 40px;
                max-width: 100%;
            }
        }
}

@keyframes slide {
    from {
        transform: translateX(0);
    }
    to {
        transform: translateX(-100%);
    }
}
    


</style>