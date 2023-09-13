<template>
  <div id="app" class="d-flex flex-column min-vh-100">
    <div class="row mx-auto py-3">
      <b-card class="m-3 p-5" title="Vixen Media" sub-title="Model Search">
        <b-form-input v-model="pcModel" class="mt-5" type="search"></b-form-input>
        <b-button @click="openPremiumContentPortals" class="mt-3 font-weight-bold" block variant="danger" type="submit">Open</b-button>
        <b-button @click="openPremiumContentBank" class="mt-3 font-weight-bold" block variant="outline-danger">Other Sites</b-button>
      </b-card>
    </div>
  </div>
</template>

<script>
const PASSWORD = "password";

export default {
  name: "App",
  data() {
    return {
      pwModel: "",
      pcModel: "",
    };
  },
  methods: {
    logIn() {
      if (this.pwModel === PASSWORD) {
        localStorage.pw = this.pwModel;
        alert("Welcome!");
        this.$refs.authForm.submit();
      } else {
        alert("Wrong!");
      }
    },
    openUrl(url) {
      window.open(url, Math.random());
    },
    openPremiumContentPortals() {
      const pcModelKebab = this.pcModel.trim().replace(/\s+/g, "-") || "videos";
      const portals = [
        "vixen.com",
        "tushy.com",
        "tushyraw.com",
        "blacked.com",
        "blackedraw.com",
        "deeper.com",
        "milfy.com",
        "slayed.com",
      ];

      portals.forEach((portal) => {
        this.openUrl(`https://www.${portal}/${pcModelKebab}`);
      });
    },
    openPremiumContentBank() {
      const pcModelKebab = this.pcModel.trim().replace(/\s+/g, "-") || "";
      const banks = [
        "tube.perverzija.com",
        "porndish.com",
        "sxyprn.com",
      ];

      banks.forEach((bank) => {
        this.openUrl(`https://${bank}/${pcModelKebab}`);
      });

      this.pcModel = "";
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
