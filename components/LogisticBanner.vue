<template>
  <div class="logistic-slider">
    <ClientOnly>
      <carousel
        :loop="true"
        :nav="false"
        :autoplay="true"
        :dots="false"
        :autoplayHoverPause="true"
        :items="2"
        :responsive="{ 0: { items: 2 }, 600: { items: 5 } }"
      >
        <div class="logistic-image" v-for="data in banner" :key="data.id">
          <img :src="data.image" />
        </div>
      </carousel>
    </ClientOnly>
  </div>
</template>

<script setups>
// import carousel from "vue-owl-carousel";

export default {
  
  components: {
    carousel:
      typeof window !== "undefined" ? () => import("vue-owl-carousel") : "",
  },
  data: () => ({
    banner: [],
  }),
  async fetch() {
    this.banner = await fetch("/Api/Banner.json").then((res) => res.json());
  },
};
</script>

<style lang="scss">
.logistic-slider {
  padding: 10px 0;
  background-color: rgb(248, 248, 248);

  .logistic-image img {
    height: 50px;
    width: fit-content;
  }
}
</style>
