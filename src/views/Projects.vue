<template>
  <section class="w-100 h-100 h-xs-auto">
    <NavigationTop />
    <NavigationBottom />

    <div class="row no-gutters w-100 h-100 page">
      <div
        v-for="a in firstTwo(projects)"
        :key="uid(a)"
        :style="{ backgroundImage: `url(${a.image})` }"
        class="col-lg-6 col-12 bg-5 has-background d-flex justify-content-center align-items-center h-100 hv-xs-100"
      >
        <div>
          <a href="#" class="text-white h4 responsive-fs_project">{{
            a.title
          }}</a>
        </div>
        <router-link
          :to="{ name: 'Project', params: { id: a.id } }"
          class="r-links"
        ></router-link>
      </div>
    </div>
    <div class="row no-gutters w-100 h-100 page">
      <div
        v-for="b in firstFour(projects)"
        :key="uid(b)"
        :style="{ backgroundImage: `url(${b.image})` }"
        class="col-lg-6 col-12 bg-5 has-background d-flex justify-content-center align-items-center h-50 h-xs-100 hv-xs-100"
      >
        <div>
          <a href="#" class="text-white h4 responsive-fs_project">{{
            b.title
          }}</a>
        </div>
        <router-link
          :to="{ name: 'Project', params: { id: b.id } }"
          class="r-links"
        ></router-link>
      </div>
    </div>
    <div class="row no-gutters w-100 h-100 page">
      <div
        v-for="c in secondTwo(projects)"
        :key="uid(c)"
        :style="{ backgroundImage: `url(${c.image})` }"
        class="col-lg-6 col-12 bg-5 has-background d-flex justify-content-center align-items-center h-100 hv-xs-100"
      >
        <div>
          <a href="#" class="text-white h4 responsive-fs_project">{{
            c.title
          }}</a>
        </div>
        <router-link
          :to="{ name: 'Project', params: { id: c.id } }"
          class="r-links"
        ></router-link>
      </div>
    </div>
    <div class="row no-gutters w-100 h-100 page">
      <div
        v-for="d in secondFour(projects)"
        :key="uid(d)"
        :style="{ backgroundImage: `url(${d.image})` }"
        class="col-lg-6 col-12 col-12 bg-5 has-background d-flex justify-content-center align-items-center h-50 h-xs-100 hv-xs-100"
      >
        <div>
          <a href="#" class="text-white h4 responsive-fs_project">{{
            d.title
          }}</a>
        </div>
        <router-link
          :to="{ name: 'Project', params: { id: d.id } }"
          class="r-links"
        ></router-link>
      </div>
    </div>
    <div class="row no-gutters w-100 h-100 page">
      <div
        v-for="e in thirdTwo(projects)"
        :key="uid(e)"
        :style="{ backgroundImage: `url(${e.image})` }"
        class="col-lg-6 col-12 bg-5 has-background d-flex justify-content-center align-items-center h-100 hv-xs-100"
      >
        <div>
          <a href="#" class="text-white h4 responsive-fs_project">{{
            e.title
          }}</a>
        </div>
        <router-link
          :to="{ name: 'Project', params: { id: e.id } }"
          class="r-links"
        ></router-link>
      </div>
    </div>
    <div class="row no-gutters w-100 h-100 page">
      <div
        v-for="f in single(projects)"
        :key="uid(f)"
        :style="{ backgroundImage: `url(${f.image})` }"
        class="col-lg-12 col-12 bg-5 has-background d-flex justify-content-center align-items-center h-100 hv-xs-100"
      >
        <div>
          <a href="#" class="text-white h4 responsive-fs_project">{{
            f.title
          }}</a>
        </div>
        <router-link
          :to="{ name: 'Project', params: { id: f.id } }"
          class="r-links"
        ></router-link>
      </div>
    </div>
  </section>
</template>

<script>
import NavigationTop from "../components/NavigationTop.vue";
import NavigationBottom from "../components/NavigationBottom.vue";
import Data from "../db.json";
export default {
  components: { NavigationTop, NavigationBottom },
  methods: {
    uid(e) {
      if (e.uid) return e.uid;
      const key = Math.random().toString(16).slice(2);
      this.$set(e, "uid", key);
      return e.uid;
    },
    firstTwo(arr) {
      return arr.slice(0, 2);
    },
    firstFour(arr) {
      return arr.slice(2, 6);
    },
    secondTwo(arr) {
      return arr.slice(6, 8);
    },
    secondFour(arr) {
      return arr.slice(8, 12);
    },
    thirdTwo(arr) {
      return arr.slice(12, 14);
    },
    single(arr) {
      return arr.slice(14, 15);
    },
  },
  mounted() {
    document.title = "Projects | ERDEM HAMZA";
  },
  data() {
    return {
      projectId: this.$route.params.id,
      projects: Data,
    };
  },
};
</script>

<style scoped>
@media (max-width: 576px) {
  .h-xs-auto {
    height: auto !important;
  }
}

@media (min-width: 576px) and (max-width: 1024px) {
  .h-xs-auto {
    height: auto !important;
  }
  .hv-xs-100 {
    height: 100vh !important;
  }
}
.fullpage-container {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
}
.page {
  position: relative;
  display: flex;
  scroll-snap-align: center;
}
section {
  scroll-snap-type: y mandatory;
  overflow-y: scroll;
}
html {
  scroll-behavior: smooth;
}
.r-links {
  position: absolute;
  width: 100%;
  height: 100%;
  cursor: url("https://demo.maharethane.com/erdem-hamza8/img/view-project-100.png"),
    auto;
}
</style>
