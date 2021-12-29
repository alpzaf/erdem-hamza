<template>
  <section id="section" class="w-100 h-100">
    <NavigationProject />
    <button class="prev-btn slick-arrow"></button>
    <slick ref="slick" :options="slickOptions">
      <div v-for="image in sources" :key="image.id">
        <div
          class="has-background d-flex align-items-center justify-content-center hv-100"
          :style="{ backgroundImage: `url(${image.src})` }"
        >
          {{ image.image }}
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
      sources: {},
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
    // let data = this.Data;
    // data.filter((item) => {
    //   console.log(item[0].images);
    // });
    console.log(this.sources[0].src);
  },
  created() {
    let projectIndex = Number(this.projectId) - 1;
    this.sources = JSON.parse(JSON.stringify(this.Data[projectIndex].images));
  },
};
</script>
