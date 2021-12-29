<template>
  <section id="section" class="w-100 h-100">
    <NavigationProject />
    <button class="prev-btn slick-arrow"></button>
    <slick ref="slick" :options="slickOptions">
      <div>
        <div
          class="has-background d-flex align-items-center justify-content-center hv-100"
          v-for="image in Data"
          :key="image.id"
          :style="{ backgroundImage: `url(${image.src})` }"
        >
          <div
            v-if="image.id == 1"
            class="text-white responsive-fs_project position-relative z-51"
          >
            {{ image.title }}
          </div>
        </div>
      </div>
    </slick>
    <button class="next-btn slick-arrow"></button>
    <NavigationBottom />
  </section>
</template>

<script>
import Slick from "vue-slick";
import "slick-carousel/slick/slick.css";
import NavigationBottom from "../components/NavigationBottom.vue";
import NavigationProject from "../components/NavigationProject.vue";
import Data from "../db.json";
export default {
  components: { Slick, NavigationBottom, NavigationProject },
  data() {
    return {
      Data,
      projectId: this.$route.params.id,
      slickOptions: {
        slidesToShow: 1,
        nextArrow: ".next-btn",
        prevArrow: ".prev-btn",
      },
    };
  },
  computed: {
    destination() {
      return Data.find((destination) => (destination.id = this.projectId));
    },
  },
  mounted() {
    let data = this.Data;
    data.filter((item) => {
      console.log(item[0].images);
    });
  },
};
</script>
