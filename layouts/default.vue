<template>
  <div id="wrap_basic" class="wrap_basic">
    <Header />
    <main id="container" class="container">
      <nuxt />
    </main>
    <Footer />
  </div>
</template>

<script>
import Header from "../components/layouts/TheHeader";
import Footer from "../components/layouts/TheFooter";

export default {
  components: {
    Header,
    Footer
  },
}
</script>

<style lang="scss" scoped>

</style>
