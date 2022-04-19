<template>
  <header class="header">
    <nuxt-link to="/manifesto">MANIFESTO</nuxt-link>
    <nuxt-link to="/">MULTIVERSE</nuxt-link>

    <nuxt-link to="/contacts">CONTACTS</nuxt-link>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
};
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
}
</style>