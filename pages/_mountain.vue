<template>
  <Page>
    <div class="page-detail">
      <nuxt-link class="back" to="/">&lt;back</nuxt-link>
      <img :src="mountain.image" alt="" />
      <div class="page-text">
        <h3>{{ mountain.title }} ({{ mountain.height }})</h3>
        <p>{{ mountain.description }}</p>
      </div>
    </div>
  </Page>
</template>

<script>
import Page from "../components/Page.vue";

export default {
  name: "Mount",
  async asyncData({ params }) {
    const request = await fetch("https://api.nuxtjs.dev/mountains");
    const response = await request.json();
    const mountain = response.find((el) => el.slug === params.mountain);
    if (mountain) {
      return {
        mountain,
      };
    } else {
      redirect("/");
    }
  },
  components: { Page },
};
</script>

<style>
.page-detail img {
  width: 100%;
  border-radius: 16px;
}

.back {
  position: absolute;
  font-size: 24px;
  text-decoration: none;
}
</style>
