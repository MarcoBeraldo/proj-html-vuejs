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

<style lang="scss" scoped>
.wwd-card {
  margin-top: 150px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 250px;
  text-align: center;

  h3 {
    font-weight: 700;
  }

  img {
    width: 150px;
    margin-bottom: 50px;
  }
}
</style>