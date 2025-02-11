<template>
  <div class="home">
    <section>
      <Baniere class="nav"/>
      <Overview class="p1-content" msg="HARMONIE DE SAINT PRIEST EN JAREZ"/>
      <BoxSponsoring class="p1-sponso"/>
    </section>
    <section>  
      <div class="deuxieme page">
        <h2>C'est la page 2</h2>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae libero molestiae nesciunt minus quam animi sequi sunt. Molestias at perferendis omnis facere sit nulla corrupti fugit quis nihil. Consectetur, error.</p>
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

document.addEventListener('wheel', (event) => {
      event.preventDefault();
      document.documentElement.scrollLeft += event.deltaY;
    }, { passive: false });

export default {
  name: 'HomeView',
  components: {
    Baniere,
    Overview, 
    //BoxSponsoring,
    EndBaniere
  },
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
    align-items: center;
    justify-content: center;
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
    background-color:  rgb(255, 249, 241)
  }

  section:nth-child(2){
    background-color:  rgb(255, 249, 241)
  } 

  section:nth-child(3){
    background-color:  #fff9f1
  } 

</style>
