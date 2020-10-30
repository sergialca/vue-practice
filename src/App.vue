<template>
  <div id="app">
    <div class="navbar">
      <img class="logo" src="@/assets/logo.png" />
      <router-link class="links" to="/">Home</router-link>
      <router-link class="links" to="/about">About</router-link>
      <router-link class="links" to="/form">Form</router-link>
      <router-view />
    </div>
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.navbar {
  width: 100%;
  height: 20px;
  background-color: #fff;
  color: #252525;
  padding: 10px 0 0 0;
  position: sticky;
  text-align: left;
  top: 0;

  .logo {
    width: 30px;
    margin-right: 40px;
    cursor: pointer;
  }
  .links {
    color: #000;
    height: auto;
    display: inline-flex;
    margin: 0 20px 0 0;
    text-decoration: none;
    vertical-align: super;
  }
  .links:active {
    color: #000;
  }

  li {
    padding: 0 15px;
  }
}
</style>
