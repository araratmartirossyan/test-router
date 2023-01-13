<template>
  <page>
    <div class="card" v-for="mountain in mountains" :key="mountain.slug">
      <img :src="mountain.image" />
      <nuxt-link :to="`/${mountain.slug}`">{{ mountain.title }}</nuxt-link>
    </div>
    <nuxt-link to="/random/:123">Generate Page</nuxt-link>
  </page>
</template>

<script>
import Page from "../components/Page.vue";

export default {
  async asyncData() {
    const res = await fetch("https://api.nuxtjs.dev/mountains");
    const mountains = await res.json();
    return {
      mountains,
    };
  },
  name: "IndexPage",
  components: { Page },
};
</script>

<style>
.card {
  border: 1px solid;
  padding: 8px;
  height: 40px;
  display: flex;
  margin-bottom: 8px;
  align-items: center;
  border-radius: 8px;
}

.card img {
  width: 60px;
  height: 40px;
  -o-object-fit: contain;
  object-fit: contain;
  margin-right: 8px;
}
</style>
