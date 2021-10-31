<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view />
  </div>
</template>

<style lang="scss">
@font-face {
  font-family: "Cloudy";
  src: url(./fonts/Cloudy/Alphasmoke-OOX6.ttf) format("truetype");
}
@font-face{
  font-family: "Sunny";
  src: url(./fonts/Sunny/101KidletSunshineBet-0OmG.ttf) format("truetype");
}
@font-face {
  font-family: "Rainy";
  src: url(./fonts/Rainy/LcrRainyDaze-P3zg.ttf) format("truetype");
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
  text-align: right;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
