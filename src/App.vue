<template>
  <div>
    <AppHeader />
    <AppMain />
    <AppFooter />
  </div>
</template>

<script>
import AppHeader from "../src/components/AppHeader.vue";
import AppMain from "../src/components/AppMain.vue";
import AppFooter from "../src/components/AppFooter.vue";

export default {
  components: { AppHeader, AppMain, AppFooter },
};
</script>

<style lang="scss">
</style>
