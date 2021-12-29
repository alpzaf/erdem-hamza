<template>
  <div
    class="top-bar d-flex justify-content-between w-100 px-5 py-5 px-xs-4 py-xs-4"
  >
    <div class="logo-holder">
      <!-- <img src="img/logo/logo-2.svg" class="logo-top" alt="Erdem Hamza Architect + Interior"> -->
      <router-link to="/" class="text-white d-block responsive-fs">
        <div>
          <h1 class="line-height-5 responsive-fs">ERDEM HAMZA</h1>
          <h1 class="line-height-5 responsive-fs">ARCHITECT +</h1>
          <h1 class="line-height-5 responsive-fs">INTERIOR</h1>
        </div>
      </router-link>
    </div>
    <div class="projects">
      <router-link
        to="/"
        class="text-white text-right d-block responsive-fs line-height-5"
        >BACK</router-link
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "NavigationProject",
  props: {},
};
</script>
