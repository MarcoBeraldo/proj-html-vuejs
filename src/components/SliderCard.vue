<template>
  <div class="card" :class="activeClass">
    <img :src="image" />

    <figcaption class="caption">
      <h2>{{ title }}</h2>
      <p>{{ text }}</p>
    </figcaption>
  </div>
</template>

<script>
export default {
  name: "SliderCard",
  props: { activeClass: String, image: String, text: String },
  data() {
    return {};
  },
};
</script>

<style>
</style>