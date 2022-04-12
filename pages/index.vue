<template>
  <div class="page">
    <div class="header">
      <nuxt-link to="manifesto">MANIFESTO</nuxt-link>
      <nuxt-link to="contacts">CONTACTS</nuxt-link>
    </div>

    <div class="main-content">
      <h1>MULTIVERSE CLUB</h1>
      <nuxt-link
        v-for="(review, i) in reviews"
        :key="i"
        :to="`reviews/${review.slug}`"
        >{{ review.title }}</nuxt-link
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "index",
  async asyncData({ $content, params, error }) {
    const reviews = await $content("reviews")
      .only(["slug", "title"])
      .fetch()
      .catch((err) => {
        error({ statusCode: 404, message: "Pagina non trovata" });
      });
    return {
      reviews,
    };
  },
};
</script>



<style>
.page {
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
}

.main-content {
  text-align: center;
}
</style>

