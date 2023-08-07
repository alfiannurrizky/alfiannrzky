<template>
  <b-navbar toggleable="lg" type="dark" fixed="top" class="shadow-lg">
    <b-navbar-toggle
      target="nav-collapse"
      style="border-radius: 0"
    ></b-navbar-toggle>

    <b-collapse
      id="nav-collapse"
      is-nav
      class="animate__animated animate__fadeInDown"
    >
      <b-navbar-nav class="n">
        <b-nav-item a href="#home">Home</b-nav-item>
        <b-nav-item a href="#about">About</b-nav-item>
        <b-nav-item a href="#projects">Projects</b-nav-item>
        <b-nav-item a href="#contact">Contact Me</b-nav-item>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</template>

<script>
require("vue-ionicons/ionicons.css");
import SunnyIcon from "vue-ionicons/dist/md-sunny.vue";
import MoonIcon from "vue-ionicons/dist/md-moon.vue";
export default {
  name: "NavBar",
  components: {
    SunnyIcon,
    MoonIcon,
  },
};
</script>
<style scoped>
.navbar-nav {
  margin-left: 100px;
  color: white;
}
@media screen and (max-width: 420px) {
  .navbar-nav {
    margin-left: 0px;
  }
}

.nav-item {
  font-size: 15px;
  margin: 15px;
  border-radius: 2px;
}
.nav-link a {
  color: #000 !important;
  text-decoration: none;
}

.bg-light {
  background: #44a08d;
  background: -webkit-linear-gradient(to right, #093637, #44a08d);
  background: linear-gradient(to right, #093637, #44a08d);
}

.n {
  border: 1px solid;
  color: #44a08d;
  border-radius: 15px;
  background: #44a08d;
  background: -webkit-linear-gradient(to right, #157475, #44a08d);
  background: linear-gradient(to right, #072122, #44a08d);
}
</style>
