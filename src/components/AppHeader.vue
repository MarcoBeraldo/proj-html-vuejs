<template>
  <header>
    <nav>
      <img src="../assets\img\white-logo-2.png" alt="Phlox Corporate" />
      <ul>
        <li v-for="(link, i) in navLinks" :key="i">
          <a href="#">{{ link }}</a>
        </li>
        <li><button type="button" class="btn btn-primary">Sign Up</button></li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
  components: {},
  data() {
    return {
      navLinks: ["Home", "About", "Services", "Blog", "Contact", "Portfolio"],
    };
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
@import "../assets/sass/_variables.scss";
header {
  height: 400px;
  background-image: linear-gradient(to bottom, $dark_blue, $night_blue);
}
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;

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