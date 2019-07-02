<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
html, body {
  margin: 0;
  padding: 0;
  width: 100%;
}

html {
  position: relative;
  min-height: 100%;
  overflow-x: hidden;
  overflow-y: scroll;
  scroll-behavior: smooth;
}

body {
  font-family: 'Montserrat', sans-serif;
}

a {
  color: unset;
  text-decoration: none;
  transition: all 0.4s;
}

#app {
  height: 100%;
  width: 100%;
  margin: 0;
  padding: 0;
}
</style>
