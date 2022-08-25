<template>
  <div>
    <div class="carousel">
      <div class="inner" ref="inner" :style="innerStyles">
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
      </div>
    </div>
    <button @click="prev">prev</button>
    <button @click="next">next</button>
  </div>
</template>

<script>
import sliderImages from "../assets/data/sliderImages.js";
import SliderCard from "./SliderCard.vue";
export default {
  components: { SliderCard },
  data() {
    return {
      sliderImages,
      activeIndex: 0,
      innerStyles: {},
      step: "600px",
      transitioning: false,
    };
  },
  mounted() {
    // this.setStep();
    this.resetTranslate();
  },
  methods: {
    // setStep() {
    //   const innerWidth = this.$refs.inner.scrollWidth;
    //   const totalCards = this.sliderImages.length;
    //   this.step = `${innerWidth / totalCards}px`;
    // },
    next() {
      if (this.transitioning) return;
      this.transitioning = true;
      this.afterTransition(() => {
        const card = this.sliderImages.shift();
        this.sliderImages.push(card);
        this.resetTranslate();
        this.transitioning = false;
        this.moveLeft();
      });
    },
    prev() {
      if (this.transitioning) return;
      this.transitioning = true;
      this.moveRight();
      this.afterTransition(() => {
        const card = this.sliderImages.pop();
        this.sliderImages.unshift(card);
        this.resetTranslate();
        this.transitioning = false;
      });
    },
    moveLeft() {
      this.innerStyles = {
        transform: `translateX(-${this.step})
                    translateX(-${this.step})`,
      };
    },
    moveRight() {
      this.innerStyles = {
        transform: `translateX(${this.step})
                    translateX(-${this.step})`,
      };
    },
    afterTransition(callback) {
      const listener = () => {
        callback();
        this.$refs.inner.removeEventListener("transitionend", listener);
      };
      this.$refs.inner.addEventListener("transitionend", listener);
    },
    resetTranslate() {
      this.innerStyles = {
        transition: "none",
        transform: `translateX(-${this.step})`,
      };
    },
  },
};
</script>

<style>
.carousel {
  overflow: hidden;
}
.inner {
  transition: transform 0.2s;
  white-space: nowrap;
}
.card {
  width: 40px;
  margin-right: 10px;
  display: inline-flex;
  /* optional */
  height: 40px;
  background-color: #39b1bd;
  color: white;
  border-radius: 4px;
  align-items: center;
  justify-content: center;
}
/* optional */
button {
  margin-right: 5px;
  margin-top: 10px;
}
</style>