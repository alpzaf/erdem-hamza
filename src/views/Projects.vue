<template>
  <section class="w-100 h-100">
    <NavigationTop />
    <NavigationBottom />

    <div class="row no-gutters w-100 h-100 page">
      <div
        v-for="project in projects"
        :key="project.id"
        :style="{ backgroundImage: `url(${project.image})` }"
        class="col-lg-6 bg-5 has-background d-flex justify-content-center align-items-center h-100"
      >
        <div>
          <a href="#" class="text-white h4">{{ project.title }}</a>
        </div>
        <router-link
          :to="{ name: 'Project', params: { id: project.id } }"
          class="r-links"
        ></router-link>
      </div>
    </div>
    <!--
    <div class="row no-gutters w-100 page">
      <div
        v-for="project in projectGrid4"
        :key="uid(project)"
        :style="{ backgroundImage: `url(${project.src})` }"
        class="col-lg-6 bg-5 has-background d-flex justify-content-center align-items-center h-50"
      >
        <div>
          <a href="#" class="text-white h4">{{ project.title }}</a>
        </div>
      </div>
    </div>
    <div class="row no-gutters w-100 page">
      <div
        v-for="project in projectGrid22"
        :key="uid(project)"
        :style="{ backgroundImage: `url(${project.src})` }"
        class="col-lg-6 bg-5 has-background d-flex justify-content-center align-items-center h-100"
      >
        <div>
          <a href="#" class="text-white h4">{{ project.title }}</a>
        </div>
      </div>
    </div>
    <div class="row no-gutters w-100 page">
      <div
        v-for="project in projectGrid44"
        :key="uid(project)"
        :style="{ backgroundImage: `url(${project.src})` }"
        class="col-lg-6 bg-5 has-background d-flex justify-content-center align-items-center h-50"
      >
        <div>
          <a href="#" class="text-white h4">{{ project.title }}</a>
        </div>
      </div>
    </div>
    <div class="row no-gutters w-100 page">
      <div
        v-for="project in projectGrid222"
        :key="uid(project)"
        :style="{ backgroundImage: `url(${project.src})` }"
        class="col-lg-6 bg-5 has-background d-flex justify-content-center align-items-center h-100"
      >
        <div>
          <a href="#" class="text-white h4">{{ project.title }}</a>
        </div>
      </div>
    </div>
    <div class="row no-gutters w-100 page">
      <div
        v-for="project in projectGrid1"
        :key="uid(project)"
        :style="{ backgroundImage: `url(${project.src})` }"
        class="col-lg-12 bg-5 has-background d-flex justify-content-center align-items-center h-100"
      >
        <div>
          <a href="#" class="text-white h4">{{ project.title }}</a>
        </div>
      </div>
    </div>
    -->
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
  },
  data() {
    return {
      projectId: this.$route.params.id,
      projects: Data,
      projectGrid2: [
        {
          id: 1,
          title: "Wu Bomonti",
          src: "https://demo.maharethane.com/erdem-hamza8/projects/wu-bomonti/wu-bomonti-1.jpg",
        },
        {
          id: 2,
          title: "Üst Kat Kuruçeşme",
          src: "https://demo.maharethane.com/erdem-hamza8/projects/ust-kat-kurucesme/ust-kat-kurucesme-1.jpg",
        },
      ],

      projectGrid4: [
        {
          id: 3,
          title: "The House Cafe Istiklal",
          src: "https://demo.maharethane.com/erdem-hamza8/projects/the-house-cafe-istiklal/the-house-cafe-istiklal-1.jpg",
        },
        {
          id: 4,
          title: "Suadiye Residence",
          src: "https://demo.maharethane.com/erdem-hamza8/projects/suadiye-residence/suadiye-residence-1.jpg",
        },
        {
          id: 5,
          title: "Soho Residence",
          src: "https://demo.maharethane.com/erdem-hamza8/projects/soho-residence/soho-residence-1.jpg",
        },
        {
          id: 6,
          title: "Shopigo No 62",
          src: "https://demo.maharethane.com/erdem-hamza8/projects/shopigo-no-62/shopigo-no-62-1.jpg",
        },
      ],

      projectGrid22: [
        {
          id: 7,
          title: "Pero Yeniköy",
          src: "https://demo.maharethane.com/erdem-hamza8/projects/pero-yenikoy/pero-yenikoy-1.jpg",
        },
        {
          id: 8,
          title: "Karaköy Project",
          src: "https://demo.maharethane.com/erdem-hamza8/projects/karakoy-project/karakoy-project-1.jpg",
        },
      ],

      projectGrid44: [
        {
          id: 9,
          title: "Kabataş Project",
          src: "https://demo.maharethane.com/erdem-hamza8/projects/kabatas-project/kabatas-project-1.jpg",
        },
        {
          id: 10,
          title: "Gökçeada Residence Project",
          src: "https://demo.maharethane.com/erdem-hamza8/projects/gokceada-residence-project/gokceada-residence-project-1.jpg",
        },
        {
          id: 11,
          title: "Gayrettepe Residence Project",
          src: "https://demo.maharethane.com/erdem-hamza8/projects/gayrettepe-residence-project/gayrettepe-residence-project-1.jpg",
        },
        {
          id: 12,
          title: "Etiler Residence Project",
          src: "https://demo.maharethane.com/erdem-hamza8/projects/etiler-residence-project/etiler-residence-project-1.jpg",
        },
      ],

      projectGrid222: [
        {
          id: 13,
          title: "Bodrum Residence Project",
          src: "https://demo.maharethane.com/erdem-hamza8/projects/bodrum-residence-project/bodrum-residence-project-1.jpg",
        },
        {
          id: 14,
          title: "BKM Mutfak Uniq",
          src: "https://demo.maharethane.com/erdem-hamza8/projects/bkm-mutfak-uniq/bkm-mutfak-uniq-1.jpg",
        },
      ],

      projectGrid1: [
        {
          id: 15,
          title: "Bebek Residence Project",
          src: "https://demo.maharethane.com/erdem-hamza8/projects/bebek-residence-project/bebek-residence-project-1.jpg",
        },
      ],
    };
  },
};
</script>

<style scoped>
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
}
</style>
