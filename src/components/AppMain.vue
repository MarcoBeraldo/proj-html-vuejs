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

    <section id="grow">
      <MainJumbotron />
    </section>

    <section id="slider">
      <ProvaSlider />
    </section>

    <section id="pricing">
      <div class="container">
        <div class="title text-center text-white">
          <h5>Price List</h5>
          <h2 class="display-4"><span class="fw-bold">Our</span> Pricing</h2>
          <p class="mb-5">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eligendi
            quia illum nisi rem?
          </p>
        </div>
        <div class="row">
          <PriceCard
            class="col-4 text-center"
            v-for="(card, i) in pricings"
            :key="i"
            :title="card.title"
            :subtitle="card.subtitle"
            :text="card.text"
            :price="card.price"
            :benefits="card.benefits"
            :bgClass="i === 1 ? 'bg-red' : 'bg-wht'"
          />
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import PriceCard from "./PriceCard.vue";
import WwdCard from "./WwdCard.vue";
import MainButton from "./MainButton.vue";
import MainJumbotron from "./MainJumbotron.vue";
import ProvaSlider from "./ProvaSlider.vue";
import activityCards from "../assets/data/activityCards.js";
import pricings from "../assets/data/pricings.js";

export default {
  components: { WwdCard, MainButton, MainJumbotron, ProvaSlider, PriceCard },
  name: "AppMain",
  data() {
    return { activityCards, pricings };
  },
  methods: {},
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
  justify-content: center nbhgvfcdx;
}
#grow {
  background-image: linear-gradient(to bottom, $dark_blue, $night_blue);
}
#slider {
  overflow: hidden;
}

#pricing {
  background-image: linear-gradient(to bottom, $dark_blue, $night_blue 60%);
  padding: 20px;
}
</style>