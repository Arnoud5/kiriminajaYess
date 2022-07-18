<template>
  <div class="pt-24 md:pt-0">
    <div class="banner-slider">
      <client-only>
        <carousel
          :loop="true"
          :nav="false"
          :autoplay="false"
          :dots="false"
          :items="1"
          :center="true"
          :stagePadding="10"
          :margin="50"
        >
          <!-- <SsrCarousel> -->

          <div class="banner-image slide" v-for="data in datas" :key="data.id">
            <div
              class="banner-placeholder md:flex md:items-center md:justify-center md:my-auto md:h-screen"
            >
              <img class="md:w-1/2" :src="data.image" />
              <div class="md:w-1/3">
                <h2>{{ data.title }}</h2>
                <p>
                  {{ data.description }}
                </p>
                <ul v-for="list in data.poin" :key="list">
                  <li>{{ list }}</li>
                </ul>
                <a class="banner-link" :href="data.link"> Daftar Disini </a>
              </div>
            </div>
          </div>
          <!-- </SsrCarousel> -->
        </carousel>
      </client-only>
    </div>
  </div>
</template>

<script setups>
// import carousel from "vue-owl-carousel";

import SsrCarousel from "vue-ssr-carousel";
import ssrCarouselCss from "vue-ssr-carousel/index.css";

export default {
  components: {
    carousel:
      typeof window !== "undefined" ? () => import("vue-owl-carousel") : "",
  },
  data: () => ({
    datas: [],
  }),
  async fetch() {
    this.datas = await fetch("/Api/main.json").then((res) => res.json());
  },
};
</script>

<style lang="scss">
.banner-slider {
  height: 100vh;
  .banner-image img {
    height: 50vh;
    width: auto;
    text-align: center;

    .banner-placeholder {
      height: auto;
    }
  }
}

h2 {
  font-size: 32px;
  font-weight: 700;
  color: rgb(0, 0, 0);
  text-align: left;
}
.banner-link {
  text-align: center;
  padding: 5px 0;
  width: 100%;
  display: block;
  background-color: rgb(166, 38, 216);
  border-radius: 20px;
  color: white;
  font-weight: 900;
}
p {
  font-size: 16px;
  font-weight: 500;
  text-align: left;
  color: rgb(0, 0, 0);
  margin: 10px 0;
}
.banner-slider {
  height: 600px;
}

ul > li {
  margin: 10px 20px;
}

li::before {
  content: "";
  background: url("../static/check.png") no-repeat center;
  background-size: 15px;
  width: 20px;
  height: 20px;
  display: inline-block;
  background-color: rgb(245, 205, 94);
  padding: 4px;
  border-radius: 20px;
  position: relative;
  left: -10px;
  bottom: -5px;
}
</style>
