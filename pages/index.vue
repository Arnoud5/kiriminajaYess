<template>
  <div>
    <Top />
    <MainBanner />
    <Navbar />
    <Footer />
  </div>
</template>

<script>
import Navbar from "../components/Navbar.vue";
import Top from "~/components/Top.vue";
import Footer from "~/components/Footer.vue";
import MainBanner from "../components/MainBanner.vue";
export default {
  name: "IndexPage",
  components: { Navbar, Top, Footer, MainBanner },
};
</script>
