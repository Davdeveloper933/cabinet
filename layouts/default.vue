<template>
  <div>
    <div class="container">
      <site-header />
      <Nuxt />
    </div>
  </div>
</template>

<script>

import SiteHeader from "~/components/header";
export default {
  name: "DefaultLayout",
  components: {SiteHeader},
};
</script>

<style lang="scss"></style>
