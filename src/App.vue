<template>
  <div class="container">
    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </nav>
    <router-view />
  </div>
</template>

<style lang="scss">
// With this Bootstrap SCSS import, can modify the colors
$primary: rebeccapurple;
@import '../node_modules/bootstrap/scss/bootstrap.scss';
</style>
