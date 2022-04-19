<template>
  <!-- <nav>
    <router-link to="/home">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav> -->
  <router-view />
</template>

<style lang="scss">
@import "./assets/font/font.css";
* {
  font-family: "简体字" !important;
}
body {
  padding: 0;
  margin: 0;
  width: 100%;
  // background-image: linear-gradient(to top, #fbc2eb 0%, #a6c1ee 100%);
  background-image: url("./assets/images/geometry2.png");
}
</style>
