<template>
  <section class="w-100 h-md-100 h-xs-100">
    <NavigationTop />
    <NavigationBottom />

    <div class="row no-gutters w-100 h-xs-100 h-md-100 page">
      <div
        v-for="a in firstTwo(projects)"
        :key="uid(a)"
        :style="{
          backgroundImage: `url(http://www.erdemhamza.com.tr/storage/projects/${a.desktop_picture})`,
        }"
        class="col-lg-6 col-12 bg-5 has-background d-flex justify-content-center align-items-center h-100 h-xs-100 h-md-100"
      >
        <div>
          <a href="#" class="text-white h4 responsive-fs_project">{{
            a.name
          }}</a>
        </div>
        <router-link
          :to="{ name: 'Project', params: { id: a.id } }"
          class="r-links"
        ></router-link>
      </div>
    </div>
  </section>
</template>

<script>
import NavigationTop from "../components/NavigationTop.vue";
import NavigationBottom from "../components/NavigationBottom.vue";
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
    if (window.innerWidth < 1025) {
      let heights = document.querySelectorAll(".bg-5");
      heights.forEach((item) => {
        item.style.minHeight = window.innerHeight + "px";
      });
    }
  },
  async created() {
    try {
      const response = await fetch(
        "http://admin.erdemhamza.com.tr/api/projects"
      );
      const data = await response.json();
      this.projects = JSON.parse(JSON.stringify(data.data));
    } catch (error) {
      console.log(error);
    }
  },
  data() {
    return {
      projectId: this.$route.params.id,
      projects: [],
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
  .h-md-100 {
    height: 100%;
  }
}

@media (min-width: 1025px) {
  .page {
    height: 100% !important;
  }
  .h-md-100 {
    height: 100% !important;
  }
  section {
    scroll-snap-type: y mandatory;
    overflow-y: scroll;
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
