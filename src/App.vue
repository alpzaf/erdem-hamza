<template>
  <router-view :key="$route.path" />
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>

<style>
@font-face {
  font-family: Everett-Regular;
  src: url("assets/fonts/Everett-Regular.otf") format("opentype");
}

@font-face {
  font-family: Everett-Regular;
  font-weight: bold;
  src: url("assets/fonts/Everett-Regular.otf") format("opentype");
}
#app {
  font-family: Everett-Regular, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  font-family: Everett-Regular;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
