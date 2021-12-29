<template>
  <section id="section" class="w-100 h-100">
    <NavigationProject />
    <!-- <button class="prev-btn slick-arrow"></button> -->
    <carousel :items="1" :dots="false">
      <div v-for="image in sources" :key="image.id">
        <div
          class="has-background d-flex align-items-center justify-content-center hv-100"
          :style="{ backgroundImage: `url(${image.src})` }"
        ></div>
      </div>
    </carousel>
    <!-- <button class="next-btn slick-arrow"></button> -->
    <NavigationBottom />
  </section>
</template>

<script>
import carousel from "vue-owl-carousel";
import NavigationBottom from "../components/NavigationBottom.vue";
import NavigationProject from "../components/NavigationProject.vue";
import Data from "../db.json";
export default {
  components: { NavigationBottom, NavigationProject, carousel },
  data() {
    return {
      title: "",
      Data,
      projectId: this.$route.params.id,
      sources: {},
    };
  },
  mounted() {
    document.title = "Project | ERDEM HAMZA";
  },
  computed: {
    destination() {
      return Data.find((destination) => (destination.id = this.projectId));
    },
  },
  created() {
    let projectIndex = Number(this.projectId) - 1;
    this.sources = JSON.parse(JSON.stringify(this.Data[projectIndex].images));
  },
};
</script>

<style>
@media (max-width: 576px) {
  .owl-prev,
  .owl-next {
    top: 53% !important;
    width: 40px !important;
    height: 40px !important;
  }
}

.owl-theme .owl-nav {
  margin: 0 !important;
}
.owl-prev,
.owl-next {
  position: absolute;
  color: transparent !important;
  background: transparent !important;
}
.owl-prev {
  left: 10%;
  transform: rotate(45deg);
}
.owl-next {
  right: 10%;
  transform: rotate(225deg);
}
.owl-prev,
.owl-next {
  top: 43%;
  border-left: 1px solid #fff;
  border-bottom: 1px solid #fff;
  border-right: none;
  border-top: none;
  background: transparent;
  z-index: 70;
  width: 120px;
  height: 120px;
}

.hv-100 {
  height: 100vh;
}

.has-background {
  position: relative;
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  /* box-shadow: inset 0px 0px 20px 20px #000000ab; */
  transition: all 200ms;
}

.has-background::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 5;
  background-color: rgba(0, 0, 0, 0.25);
}

.has-background a {
  position: relative;
  z-index: 10;
}
</style>
