<template>
  <div>
    <Top />
    <About />
    <Navbar />
    <Footer />
  </div>
</template>

<script>
import Navbar from "~/components/Navbar.vue";
import Top from "~/components/Top.vue";
import Footer from "~/components/Footer.vue";
import About from "~/components/About.vue";
export default {
  name: "AboutPage",
  components: { Navbar, Top, Footer, About },
};
</script>

<style lang="scss">
  .home{
    background-color: rgba(255, 177, 255, 0.568);
  }

</style>
