<template>
  <!-- <NavBar /> -->
  <Logo />
  <!-- <DefaultFooter /> -->
  <div class="page-container">
    <div class="not-found-container">
      <div class="error-404">404</div>
      <div class="error-message">
        <span class="oops-message"> OOPS! </span>
        <span class="actual-message"> That page doesn't exist </span>
      </div>
      <button class="error-button" @click="landing()">Return to Home</button>
    </div>
  </div>
</template>

<script>
// import NavBar from "@/components/NavBar.vue";
import Logo from "@/components/Logo.vue";

export default {
  components: { Logo },

  methods: {
    landing() {
      if (this.$store.state.type == "tourist") {
        this.$router.push("/touristProfile");
      } else if (this.$store.state.type == "tour-guide") {
        this.$router.push("/tourGuideProfile");
      } else {
        this.$router.push("/");
      }
    },
  },
};
</script>

<style scoped>
.page-container {
  display: flex;
  height: 100%;
  align-items: center;
}

.error-404 {
  font-family: Ubuntu;
  font-size: 300px;
  /* display: flex; */
  color: #337e8f;
  margin: -60px;
}

.error-message {
  flex-direction: column;
  align-items: center;
  display: flex;
}

.oops-message {
  font-size: 70px;
  margin-bottom: -25px;
}

.actual-message {
  font-size: 50px;
}

.error-button {
  width: 50%;
  padding: 12px 20px;
  margin: 25px 0px;
  box-sizing: border-box;
  border-radius: 50px;
  color: white;
  background-color: #337e8f;
}

.not-found-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
