<template>
  <header class="header">
    <div class="nav">
      <nuxt-link to="/manifesto">MANIFESTO</nuxt-link>
      <nuxt-link to="/">MULTIVERSE</nuxt-link>

      <nuxt-link to="/contacts">CONTACTS</nuxt-link>
    </div>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
};
</script>

<style lang="scss" >
.header {
  position: fixed;
  left: 0;
  top: 0;
  width: 100vw;

  overflow: hidden;
  // background-color: white;

  .nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1% 2%;
  }
}
</style>