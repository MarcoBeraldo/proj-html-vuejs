<template>
  <nav>
    <img src="../assets\img\white-logo-2.png" alt="Phlox Corporate" />
    <ul>
      <li v-for="(link, i) in navLinks" :key="i">
        <a href="#">{{ link }}</a>
      </li>
      <li>
        <MainButton />
      </li>
    </ul>
  </nav>
</template>

<script>
import MainButton from "./MainButton.vue";
export default {
  name: "NavBar",
  components: { MainButton },
  data() {
    return {
      navLinks: ["Home", "About", "Services", "Blog", "Contact", "Portfolio"],
    };
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
@import "../assets/sass/style.scss";
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 20px;
  padding-bottom: 50px;

  ul {
    list-style-type: none;
    display: flex;

    li {
      margin-right: 20px;
      display: flex;
      align-items: center;

      a {
        text-decoration: none;
        color: $white;
      }
    }
  }
}
</style>