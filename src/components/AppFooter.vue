<template>
  <footer>
    <div class="container">
      <div class="upper-footer">
        <div class="row justify-content-around">
          <div class="col-3 d-flex-col">
            <img src="../assets\img\white-logo-2.png" alt="Phlox Corporate" />
            <p>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestias
              voluptas, alias ducimus, nisi labore incidunt a quia repudiandae,
              delectus vel quisquam corrupti cumque architecto voluptatibus
              adipisci. Consectetur blanditiis atque ratione?
            </p>
          </div>

          <div class="col-2">
            <ul>
              <li class="text-white fs-4">Quick Links</li>
              <li v-for="(link, i) in quickLinks" :key="i">
                <a href="#">{{ link }}</a>
              </li>
            </ul>
          </div>

          <div class="col-2">
            <ul>
              <li class="text-white fs-4">Resources</li>
              <li v-for="(link, i) in otherLinks" :key="i">
                <a href="#">{{ link }}</a>
              </li>
            </ul>
          </div>

          <div class="col-4">
            <h4 class="text-white">Contact Us</h4>
            <p class="my-5">
              <span class="text-white">Address: </span> Patricia C. Amedee 4401
              Waldeck <br />
              Street Grapevine Nashville, Tx 76051
            </p>
            <p><span class="text-white">Phone: </span>+99 (0) 101 0000 888</p>
            <p><span class="text-white">Email: </span>info@yourdomain.com</p>
          </div>
        </div>
      </div>

      <div class="lower-footer d-flex justify-content-between">
        <p>&copy; 2020 Phlox. All Rights Reserved.</p>
        <div class="icons">
          <font-awesome-icon
            icon="fa-brands fa-instagram"
            class="mx-3 fs-6 text-white"
          />
          <font-awesome-icon
            icon="fa-brands fa-linkedin-in"
            class="mx-3 fs-6 text-white"
          />
          <font-awesome-icon
            icon="fa-brands fa-facebook-f"
            class="mx-3 fs-6 text-white"
          />
          <font-awesome-icon
            icon="fa-brands fa-twitter"
            class="mx-3 fs-6 text-white"
          />
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "AppFooter",
  components: {},
  data() {
    return {
      quickLinks: ["Services", "Contact", "Blog"],
      otherLinks: [
        "Art Design",
        "Computer",
        "IT News",
        "Networking",
        "Web Security",
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/sass/style.scss";
footer {
  background-color: $footer_blue;
  color: $dark_gray;
  padding-top: 50px;
  .upper-footer {
    border-bottom: 1px solid gray;
  }
  .lower-footer {
    padding-top: 20px;
  }
  img {
    margin-bottom: 40px;
  }
  h4 {
    margin-top: 20px;
  }
  ul {
    list-style-type: none;

    li {
      margin-top: 15px;
    }

    a {
      text-decoration: none;
      color: $dark_gray;
    }
  }
}
</style>