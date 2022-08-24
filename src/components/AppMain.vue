<template>
  <main>
    <section id="what-we-do">
      <div class="container">
        <div class="title text-center">
          <h4>Our Services</h4>
          <h2>What We Do</h2>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eligendi
            quia illum nisi rem?
          </p>
        </div>
        <div class="card-container d-flex">
          <WwdCard
            v-for="(activityCard, index) in activityCards"
            :key="index"
            :title="activityCard.title"
            :image="activityCard.image"
            :text="activityCard.text"
          />
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import WwdCard from "./WwdCard.vue";
export default {
  components: { WwdCard },
  name: "AppMain",
  data() {
    return {
      activityCards: [
        {
          text: "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Soluta dicta similique fuga officia nemo error",
          title: "Data Analisys",
          image: "../src/assets/img/group-0.png",
        },
        {
          text: "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Soluta dicta similique fuga officia nemo error",
          title: "SEO Optimization",
          image: "../assets/img/group-1.png",
        },
        {
          text: "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Soluta dicta similique fuga officia nemo error",
          title: "Security Data",
          image: "../assets/img/group-2.png",
        },
        {
          text: "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Soluta dicta similique fuga officia nemo error",
          title: "Branding Strategy",
          image: "../assets/img/group-3.png",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
</style>