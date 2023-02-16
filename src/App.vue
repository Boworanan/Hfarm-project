<template>
  <nav>
    <router-link to="/">
      <img alt="home" src="./assets/home_logo.png" style="width: 28px;" />
      Home </router-link>
    <router-link to="/farm">
      <img alt="farm" src="./assets/sprout_logo.png" style="width: 28px;padding-left: 5px;"/>
      Farm </router-link>
    </nav>
    <router-view/>
  </template>
  
  <style>
  
  @import url('https://fonts.googleapis.com/css2?family=Manrope&display=swap');
body{
  background-color: #e4f2ce ;
}
#app {
  font-family: 'Manrope', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
  
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  font-size: 34px;
  text-decoration: none;
  overflow: hidden;
}

nav a.router-link-exact-active {
  color: #229963;
}
</style>
