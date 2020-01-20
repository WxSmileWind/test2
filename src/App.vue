<template>
  <div id="app">
<!--    <div id="nav">-->
<!--      <router-link to="/?id=11">Home</router-link> |-->
<!--      <router-link to="/about?id=22">About</router-link>-->
<!--      <a href="#/list">跳转至list页面</a>-->
<!--    </div>-->

    <router-view />
  </div>
</template>
<style lang="scss">
  body{
    margin: 0px;
    padding: 0px;
    background-color: #f2f5f6;
  }
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0;
  padding: 0;

}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
