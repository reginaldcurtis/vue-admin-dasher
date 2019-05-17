<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
@import "@/global-styles/colors.scss";
@import "@/global-styles/typography.scss";

body {
  background: $light-grey;
}
h1 {
  @include heading-1;
}

p {
  @include large-text-bold($purple);
}
#app {
  font-family: $system-font-family;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: $blue-grey;
}
#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: $blue-grey;
    &.router-link-exact-active {
      color: $blue-grey;
    }
  }
}
</style>
