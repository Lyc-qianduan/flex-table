<!--
 * @Author: your name
 * @Date: 2020-10-20 17:06:27
 * @LastEditTime: 2020-10-20 17:11:58
 * @LastEditors: your name
 * @Description: In User Settings Edit
 * @FilePath: /flex-table/src/App.vue
-->
<template>
  <div id="app">
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
