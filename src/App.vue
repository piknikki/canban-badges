<template>
  <div id="app">
    <div id="nav">
      <span>
        <img class="logo" src="../src/assets/giddyuplogo.png" alt="Giddyup Logo">
      </span>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  line-height: 2;
  font-size: large;
}

#nav {
  font-size: 1.5em;
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;
    padding: 10px;

    &.router-link-exact-active {
      color: #14AABF;
    }
  }
}

.logo {
  width: 50px;
}

.box {
  background-color: aliceblue;
}
</style>
