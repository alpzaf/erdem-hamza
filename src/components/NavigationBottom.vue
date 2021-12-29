<template>
  <div
    class="bottom-bar d-flex justify-content-between w-100 px-5 py-5 px-xs-4 py-xs-4"
  >
    <div>
      <router-link to="/contact" class="text-white responsive-fs"
        >CONTACT</router-link
      >
    </div>
    <div>
      <a
        href="https://www.instagram.com/erdemhamza/"
        class="text-white responsive-fs"
        target="_blank"
        >INSTAGRAM</a
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "NavigationBottom",
  props: {},
};
</script>
