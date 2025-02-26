<template>
  <div class="home">
    <section>
      <ProgressBar/>
      <Baniere class="navigation"/>
      <Overview class="p1-content"/>
    </section>
    <section class="deuxieme-page"> 
      <h2>Représentation Année 2025</h2>
        <div class="cards-container">
          <Card imageUrl="/assetsDynamic/sax.jpg"
                tittle="Concert"
                description="Invitation de l'Harmonie de la Chazotte"
                date="Sam. 15 mar"
                place="La Talaudière"/>
          <Card imageUrl="/assetsDynamic/sax.jpg"
                tittle="Commémoration"
                date="Mer. 19 mar"
                place="St Priest en Jarez"/>
          <Card imageUrl="/assetsDynamic/sax.jpg"
                tittle="Concert"
                description="Invitation de l'Harmonie de Côte Chaude"
                date="Sam. 5 avr"
                place="St Genest Lerps"/>
          <Card imageUrl="/assetsDynamic/sax.jpg"
                tittle="Commémoration"
                date="Jeu. 8 mai"
                place="St Priest en Jarez"/>
          <Card imageUrl="/assetsDynamic/sax.jpg"
                tittle="Concert Annuel"
                description="Au NEC"
                date="Sam. 17 mai"
                place="St Priest en Jarez"/> 
          <Card imageUrl="/assetsDynamic/sax.jpg"
                tittle="Fête de la musique"
                date="Sam. 21 jun"
                place="St Priest en Jarez"/>  
          </div>          
    </section>
    <section class="troisieme-page">
        <!--<h2>C'est la page 3</h2>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Temporibus quas, asperiores non molestias accusamus possimus eos voluptatum, nam labore rem accusantium dolorum odio nulla corporis ex voluptas modi distinctio placeat.</p>-->
      <div class="sponsor">
        <h3 class="sponsor-tittle">Un grand <br> merci à nos partenaires</h3>
        <BoxSponsoring class="sponsor-content"/>
      </div>
      <EndBaniere class="end"/>
    </section>
  </div>
</template>

<script>

import ProgressBar from '@/components/ProgressBar.vue';
import Baniere from '@/components/Baniere.vue';
import BoxSponsoring from '@/components/BoxSponsoring.vue';
import EndBaniere from '@/components/EndBaniere.vue';
import Overview from '@/components/Overview.vue'
import Card from '@/components/Card.vue'

export default {
  name: 'HomeView',
  components: {
    Baniere,
    Overview, 
    BoxSponsoring,
    EndBaniere,
    Card,
    ProgressBar
  },

  mounted() {
    // Gestion du scroll avec la molette de la souris
    document.addEventListener('wheel', this.handleWheel, { passive: false });

    // Gestion du slide trackpad avec le toucher
    document.addEventListener('touchstart', this.handleTouchStart, { passive: true });
    document.addEventListener('touchmove', this.handleTouchMove, { passive: false });
  },
  methods: {
    handleWheel(event) {
      event.preventDefault();
      document.documentElement.scrollLeft += event.deltaY;
    },
    handleTouchStart(event) {
      this.startX = event.touches[0].clientX;
    },
    handleTouchMove(event) {
      event.preventDefault();
      let touchX = event.touches[0].clientX;
      let deltaX = this.startX - touchX;
      document.documentElement.scrollLeft += deltaX * 1.5; // Facteur pour ajuster la vitesse
      this.startX = touchX;
    }
  },
  beforeUnmount() {
    document.removeEventListener('wheel', this.handleWheel);
    document.removeEventListener('touchstart', this.handleTouchStart);
    document.removeEventListener('touchmove', this.handleTouchMove);
  }
} 
</script>

<style lang="scss" scoped>
  .home {
    margin: 0;
    padding: 0;
    display: flex;

  }

  section{
    display: flex;
    align-items: flex-end;
    //
    flex: none;
    height: 100vh;
    width: 100%;
    color:#292929;
    position: relative;
  }
  .navigation{
    position: fixed;
    left: 0;
    z-index: 2;
  }

  .end{
    position: absolute;
    right: 0;
    z-index: 2;
  }

  .p1-content{

  }



  section:nth-child(1){
    background: url('/src/assets/pexels-snapwire-358731.jpg') no-repeat center center;
    background-size: cover;
    background-position: 40% center;
   //Filter: grayscale(100%);
    justify-content: flex-end;  
  }
  .deuxieme-page{
    background-color:rgb(255, 255, 255);
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    flex-direction: column;
  }

  .cards-container{
      display: flex;
      flex-wrap: wrap;
      justify-content: center; 
    }


  .troisieme-page{
    background-color: rgb(255, 255, 255);
    position: relative;
    .sponsor{
      position: absolute;
      bottom: 0;
      right: 0;
      display: flex;
      justify-content: space-between;
      .sponsor-tittle{

        width: 33vw;      }
      .sponsor-content{
        width: 66vw;
      }
    } 
  }


</style>
