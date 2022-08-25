<template>
  <div class="card" :class="activeClass">
    <figure>
      <img :src="image" />

      <figcaption class="caption">
        <h4>{{ title }}</h4>
        <p>{{ text }}</p>
      </figcaption>
    </figure>
  </div>
</template>

<script>
export default {
  name: "SliderCard",
  props: { activeClass: String, image: String, text: String, title: String },
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
.card {
  min-width: 600px;
  border-radius: 30px;
  margin: 0 20px;

  img {
    width: 100%;
    border-radius: 30px;
  }

  figcaption {
    display: flex;
    justify-content: space-between;
    padding: 10px;
  }
}
</style>