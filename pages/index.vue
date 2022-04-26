<template>
  <div class="page">
    <div class="main-content">
      <h2>MULTIVERSECLUB IT</h2>
      <div class="reviews">
        <div class="card">
          <img src="~/assets/images/dbf.jpg" alt="" />
          <br />
          <div class="card-info">
            <nuxt-link
              v-for="(review, i) in reviews"
              :key="i"
              :to="`reviews/${review.slug}`"
              >{{ review.title }}</nuxt-link
            >
          </div>
        </div>
        <div class="card">
          <img src="~/assets/images/dbf.jpg" alt="" />
          <br />
          <div class="card-info">
            <nuxt-link
              v-for="(review, i) in reviews"
              :key="i"
              :to="`reviews/${review.slug}`"
              >{{ review.title }}</nuxt-link
            >
          </div>
        </div>
      </div>

      <h6>SAVE THE ITALIAN SCENE</h6>
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



<style lang="scss" scoped>
@import "@/styles/main.scss";
.page {
  text-align: center;

  h2 {
    font-size: 256px;
  }

  .reviews {
    .card {
      img {
        width: 350px;
        transition: 150ms ease-in-out;
      }
      border: 1px solid black;
      border-radius: 10px;
      padding: 25px;

      box-shadow: 10px 10px black;
      transition: 150ms ease-in-out;
    }

    .card:hover {
      img {
        padding: 15px;
        transition: 150ms ease-in-out;
      }
      box-shadow: 20px 20px black;
      transition: 150ms ease-in-out;
    }
    .card-info {
      padding-top: 15px;
      font-size: 22px;
    }

    display: flex;
    justify-content: space-evenly;
  }
}
</style>

