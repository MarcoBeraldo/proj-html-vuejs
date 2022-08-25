<template>
  <div>
    <i
      class="fa-solid fa-circle-arrow-left fa-2x"
      id="prev"
      @click="isFirst ? (activeIndex = images.length - 1) : activeIndex--"
    ></i>

    <i
      class="fa-solid fa-circle-arrow-right fa-2x"
      id="next"
      @click="isLast ? (activeIndex = 0) : activeIndex++"
    ></i>

    <div class="d-flex justify-content-center my-5">
      <SliderCard
        v-for="(img, i) in sliderImages"
        :key="i"
        :title="img.title"
        :text="img.text"
        :image="img.image"
        :activeClass="activeIndex === i ? 'item active' : 'item'"
      />
    </div>

    <div id="thumbnail" class="d-flex justify-content-center">
      <div
        class="dot"
        v-for="(img, i) in sliderImages"
        :key="i"
        @click="setCentral()"
      ></div>
    </div>
  </div>
</template>

<script>
import sliderImages from "../assets/data/sliderImages.js";
import SliderCard from "./SliderCard.vue";
export default {
  name: "MainSlider",
  data() {
    return {
      activeIndex: 0,
      sliderImages,
    };
  },
  components: { SliderCard },
  computed: {
    isFirst() {
      return this.activeIndex === 0;
    },
    isLast() {
      return this.activeIndex >= this.images.length - 1;
    },
  },

  methods: {
    setActive(index) {
      this.activeIndex = index;
    },
    setCentral(index) {
      this.activeIndex = index;
      return (this.activeIndex += 1);
    },
  },
};
</script>

<style lang="scss" scoped>
.dot {
  display: block;
  margin: 0 1em;
  width: 1em;
  height: 1em;
  background: rgba(0, 0, 0, 0.3);
  border-radius: 100px;
}
</style>