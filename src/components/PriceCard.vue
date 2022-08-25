<template>
  <div class="price-card-container">
    <div class="price-card" :class="bgClass">
      <h3 class="display-5 fw-bold">{{ title }}</h3>
      <h6>{{ subtitle }}</h6>
      <p class="text-start px-5 ms-5 mb-0 mt-3">$</p>
      <p class="display-1 my-0 fw-bolder">{{ price }}</p>
      <p class="mb-5">Per Month</p>
      <ul>
        <li v-for="(benefit, i) in benefits" :key="i">{{ benefits[i] }}</li>
      </ul>
      <MainButton />
    </div>
  </div>
</template>

<script>
import pricings from "../assets/data/pricings.js";
import MainButton from "./MainButton.vue";
export default {
  name: "PriceCard",
  components: { MainButton },
  data() {
    return {
      pricings,
    };
  },
  props: {
    title: String,
    subtitle: String,
    text: String,
    price: String,
    benefits: Array,
    bgClass: String,
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
@import "../assets/sass/style.scss";
.price-card-container {
  padding: 20px;
}

.price-card {
  border-radius: 30px;
  padding: 20px;
  box-shadow: 0 50% 18px $shadow_gray;
  &.bg-wht {
    background-color: $white;
  }

  &.bg-red {
    background-image: linear-gradient(125deg, $purple, $red);
    color: white;
  }

  ul {
    list-style-type: none;
    margin-bottom: 100px;

    li {
      margin-top: 20px;
    }
  }
}
</style>