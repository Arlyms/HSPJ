<template>
  <div class="home">
    <section>
      <Baniere class="nav"/>
      <Overview class="p1-content" msg=" I LOVE U" imageUrl="/assetsDynamic/chat.jpg"/>
      <BoxSponsoring class="p1-sponso"/>
    </section>
    <section>  
      <div class="deuxieme page">
        <Card title="Blabla"
              description="Blablabla"/>
      </div>
    </section>
    <section>
      <div class="troisieme page">
        <h2>C'est la page 3</h2>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Temporibus quas, asperiores non molestias accusamus possimus eos voluptatum, nam labore rem accusantium dolorum odio nulla corporis ex voluptas modi distinctio placeat.</p>
      </div>
      <EndBaniere class="end"/>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
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
    //BoxSponsoring,
    EndBaniere,
    Card
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
    flex-direction: column;
    align-items: flex-end;
    justify-content: flex-end;
    flex: none;
    height: 100vh;
    width: 100%;
    color:#292929;
    position: relative;
  }
  .nav{
    position: fixed;
    left: 0;
    z-index: 2;
  }

  .end{
    position: absolute;
    right: 0;
    z-index: 2;
  }
  .p1-sponso{
    position: absolute;
    bottom: 0;
  }

  section:nth-child(1){
    background: url('/src/assets/pexels-snapwire-358731.jpg') no-repeat center center;
    background-size: cover;
    background-position: 40% center;
    filter: grayscale(100%);
  }

  section:nth-child(2){
    background-color:  rgb(255, 249, 241)
  } 

  section:nth-child(3){
    background-color:  #fff9f1
  } 

</style>
