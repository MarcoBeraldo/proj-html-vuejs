<template>
  <main>
    <section id="what-we-do">
      <div class="container">
        <div class="title text-center">
          <h5>Our Services</h5>
          <h2 class="display-4"><span class="fw-bold">What</span> We Do</h2>
          <p class="mb-3">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eligendi
            quia illum nisi rem?
          </p>
        </div>
        <div class="card-container d-flex justify-content-between">
          <WwdCard
            v-for="(activityCard, index) in activityCards"
            :key="index"
            :title="activityCard.title"
            :image="activityCard.image"
            :text="activityCard.text"
          />
        </div>
        <div class="button">
          <MainButton />
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import WwdCard from "./WwdCard.vue";
import MainButton from "./MainButton.vue";
import activityCards from "../assets/data/activityCards.js";
export default {
  components: { WwdCard, MainButton },
  name: "AppMain",
  data() {
    return { activityCards };
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/sass/style.scss";
h5 {
  color: $red;
  margin-top: 100px;
}
h2 {
  margin-bottom: 20px;
}
.button {
  margin: 150px 0;
  display: flex;
  justify-content: center;
}
</style>