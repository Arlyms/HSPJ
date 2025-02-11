<template>
    <div class="banner">
        <div class="banner-content">
            <div class="banner--logo">
                <img src="@/assets/logo/logo-harmonie.png" alt="nom de l'harmonie saint priest en jarez">
            </div> 
            <div class="banner--reseaux">
                <p><a href="https://www.facebook.com/hmspj" target="_blank"><img src="@/assets/logo/facebook.svg" alt="logo facebook"></a></p>
                <p><a href="https://www.instagram.com/harmonie_spj/?hl=fr" target="_blank"><img src="@/assets/logo/insta.svg" alt="logo instagram"></a></p>
                
            </div>   
        </div>
        <div class="banner-background">
            <img src="@/assets/banner/cle_de_sol_.svg" alt="clés de sol">
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style lang="scss" scoped>

.banner{
    position: relative;
    width: 200px;
    height: 100vh;

    .banner-content{
        z-index: 1;
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        display: flex;
        flex-wrap: wrap;
        flex-direction: column;
        align-content: space-between;

        .banner--logo{
            margin: 15px;
            margin-top: 30px;
            img{
            width: 60%;
            }
        }
        .banner--reseaux{
            position: absolute;
            margin-bottom: 40px;
            bottom: 20px;
            right: 20px; 
            z-index: 2; 
            padding: 10px;
            border-radius: 8px;
            display: flex;
            flex-direction: column;
            align-items: flex-end;
            p {
                margin: 5px 0;

                img{
                    width: 3em;
                }
            }       
        }

    }
    .banner-background{
        z-index: 0;
        width: 100%;
        height: 100%;
        background: url('/src/assets/banner/paper.jpg') no-repeat center center;
        background-size: cover;
        display: flex;
        align-items: center;
        justify-content: center;
        overflow: hidden;
        box-shadow: 10px 0px 15px rgba(0, 0, 0, 0.2);
        
        img{
            height: 460%;
            padding-left:150px;
            padding-bottom: 50px;
        }
    }

}    
</style>