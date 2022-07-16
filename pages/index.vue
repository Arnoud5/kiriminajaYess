<template>
  <div>
    <Top />
    <MainBanner />
    <ClientBanner />
    <LogisticBanner />
    <Navbar />
    <Footer />
  </div>
</template>

<script>
import Navbar from "../components/Navbar.vue";
import Top from "~/components/Top.vue";
import Footer from "~/components/Footer.vue";
import LogisticBanner from "../components/LogisticBanner.vue";
import MainBanner from "../components/MainBanner.vue";
import ClientBanner from "~/components/ClientBanner.vue";
export default {
  name: "IndexPage",
  components: { Navbar, Top, Footer, LogisticBanner, MainBanner, ClientBanner },
};
</script>

<style lang="scss">
  .home{
    background-color: rgba(255, 177, 255, 0.568);
  }

</style>
