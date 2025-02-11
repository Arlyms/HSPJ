<template>
  <!--<nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/contact">Contact</router-link>
  </nav>-->
  <router-view/>
</template>

<style>

@font-face {
    font-family: "TT";
    src: url("/src/font/TTHoves/TT\ Hoves\ Pro\ Trial\ Medium.ttf") format("truetype");
}

html,body {
  margin: 0;
  padding: 0;
  background-color:   rgb(61, 61, 61);
}

#app {
  font-family: "TT", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #8a7500;




  /*changer la typo*/ 
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50; /*couleurs pour la navigation inactive*/ 
}

nav a.router-link-exact-active {
  color: #0306db; /*couleurs pour la navigation active*/ 
}
</style>
