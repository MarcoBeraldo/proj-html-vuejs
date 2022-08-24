<template>
  <header>
    <div class="container">
      <NavBar />
      <MainJumbotron />
    </div>
  </header>
</template>

<script>
import MainJumbotron from "./MainJumbotron.vue";
import NavBar from "./NavBar.vue";
export default {
  name: "AppHeader",
  components: { MainJumbotron, NavBar },
  data() {
    return {};
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
@import "../assets/sass/style.scss";
header {
  background-image: linear-gradient(to bottom, $dark_blue, $night_blue);
  padding-bottom: 150px;
}
</style>