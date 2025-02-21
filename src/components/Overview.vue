<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      Nous sommes un groupe de plus de 50 musiciens<br> sous la baguette de notre directeur musical <strong>Eric Bernoux</strong><br>
      L&apos;harmonie a été formée en 1993. Au cours des années,<br> notre programme s&apos;est amusé de morceaux parfois simples et entraînants,<br>parfois plus techniques et rigoureux, allant des ballades les plus calmes<br> aux classiques les plus virtuoses, en passant par les incontournables musiques de films.
      <!-- <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.-->
    </p>
  </div>
</template>

<script>
export default {
  name: 'Overview',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  padding: 50px;
  margin: 100px;
  background: url('/src/assets/banner/paper.jpg') no-repeat center center;
  background-size: cover;
  border-radius: 20px;
}

p{
  text-align: justify;
}

h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #a70000; /* couleur scopé au copomnent*/
}
</style>
