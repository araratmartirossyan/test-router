<template>
  <Page>
    <nuxt-link class="back" to="/">&lt;back</nuxt-link>

    <div class="content">
      This is dynamically generated page

      <h4>Current Path:</h4>
      <pre>{{ JSON.stringify(params) }} </pre>
    </div>
  </Page>
</template>

<script>
import Page from "../components/Page.vue";

export default {
  async asyncData({ params }) {
    return {
      params,
    };
  },
  components: {
    Page,
  },
};
</script>

<style>
.content {
  margin-top: 60px;
}

pre {
  background: black;
  color: white;
  padding: 8px;
}
</style>
