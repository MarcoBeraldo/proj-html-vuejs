<template>
  <div class="wwd-card">
    <img :src="image" :alt="title" />
    <h3>{{ title }}</h3>
    <p>
      {{ text }}
    </p>
  </div>
</template>

<script>
export default {
  name: "WwdCard",
  props: { title: String, image: String, text: String },
};
</script>

<style>
</style>