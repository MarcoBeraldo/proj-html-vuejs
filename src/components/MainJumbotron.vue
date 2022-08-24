<template>
  <section id="main-jumbotron">
    <div class="container">
      <div class="row align-items-center justify-content-between">
        <div class="col-5">
          <h2 class="text-white display-4 fw-bold">Business Planning</h2>
          <h3 class="text-white display-4">Digital Technology</h3>
          <h2 class="text-white display-4 fw-bold">Modern Solution!</h2>
          <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Temporibus
            quaerat repellat ipsa quasi repellendus ratione tempora
          </p>
          <div class="buttons d-flex">
            <MainButton />
            <MainButton />
          </div>
        </div>
        <div class="col-6">
          <img src="../assets\img\header.png" alt="" />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import MainButton from "./MainButton.vue";
export default {
  name: "MainJumbotron",
  components: { MainButton },
};
</script>

<style lang="scss" scoped>
@import "../assets/sass/_variables.scss";

p {
  color: $light_blue;
}

img {
  max-width: 100%;
}
</style>