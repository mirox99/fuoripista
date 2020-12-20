<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
@import "assets/scss/typography";

body {
  margin: 0;
  padding: 0;

  &::-webkit-scrollbar {
    display: none;
  }

  -ms-overflow-style: none;
  scrollbar-width: none;

  p, h1, h2, a {
    margin: 0;
    padding: 0;
    outline: none;
  }

  * {
    box-sizing: border-box;
  }
}
</style>
