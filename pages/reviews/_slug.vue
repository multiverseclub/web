<template>
  <div class="main-content">
    <div class="cover">
      <img src="~/assets/images/dbf.jpg" alt="DBF" />
    </div>

    <nuxt-content :document="page" class="page" />
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params, error }) {
    const page = await $content("reviews/" + params.slug || "index")
      .fetch()
      .catch((err) => {
        error({ statusCode: 404, message: "Pagina non trovata" });
      });
    return {
      page,
    };
  },
};
</script>

<style lang="scss" scoped>
.main-content {
  display: flex;
  flex-direction: row;
  text-align: left;
  max-width: 80%;
  margin: auto;
  padding-top: 5%;
  padding-bottom: 5%;
  img {
    height: 500px;
  }

  .cover {
    margin: auto;
    justify-content: center;
    padding: 8%;
  }

  align-items: center;
}
</style>