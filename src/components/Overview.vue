<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      Nous sommes un groupe de plus de 50 musiciens<br> sous la baguette de notre directeur musical <strong>Eric Bernoux</strong><br>
      L&apos;harmonie a été formée en 1993. Au cours des années,<br> notre programme s&apos;est amusé de morceaux parfois simples et entraînants,<br>parfois plus techniques et rigoureux, allant des ballades les plus calmes<br> aux classiques les plus virtuoses, en passant par les incontournables musiques de films.
    </p>
  </div>
</template>

<script>
export default {
  name: 'Overview',
  props: {
    msg: String,
    imageUrl: String
  }
}
</script>


<style lang="scss" scoped>
.hello {
  padding: 5vh;
  margin: 10vw;
  background: url('/src/assets/banner/paper.jpg') no-repeat center center;
  background-size: cover;
  // border-radius: 20px;
}

p{
  text-align: justify;
  font-size: 1.5rem; 
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
  color: #a70000; 
}

</style>
