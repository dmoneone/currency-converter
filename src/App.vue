<template>
  <div id="app">
    <div class="container">
        <div id="nav">
          <router-link to="/">Home</router-link> |
          <router-link to="/calculator">Calculator</router-link>
        </div>
    </div>
    <router-view/>
  </div>
</template>

<style lang="scss">
    #app {
      font-family: 'Avenir', Helvetica, Arial, sans-serif;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      color: #2c3e50;
    }
    #nav {
      margin-top: 50px;
      padding-bottom: 30px;
      display: block;
      a {
        font-weight: bold;
        color: #2c3e50;
        &.router-link-exact-active {
          color: #42b983;
        }
      }
    }
</style>
