<template>
  <div id="app">
    <AppHeader />
  </div>
</template>

<script>
import AppHeader from "/src/components/AppHeader.vue";
// import AppMain from "/src/components/AppMain.vue";
// import AppFooter from "/src/components/AppFooter.vue";

export default {
  name: "App",
  components: {
    AppHeader,
    //  AppMain,
    //  AppFooter
  },
  data() {
    return {};
  },
  methods: {},
};
</script>

<style lang="scss">
@import "assets/sass/style.scss";
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
</style>
