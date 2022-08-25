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

    <SliderCard
      v-for="(img, i) in sliderImages"
      :key="i"
      :title="img.title"
      :text="img.text"
      :image="img.image"
      :activeClass="activeIndex === i ? 'item active' : 'item'"
    />

    <div id="thumbnail">
      <img
        v-for="(img, i) in sliderImages"
        :key="i"
        :activeClass="activeIndex === i ? 'thumb active' : 'thumb'"
        @click="setActive(i)"
      />
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
  components: SliderCard,
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
  },
};
</script>

<style lang="scss" scoped>
</style>