<template>
  <div id="app" class="d-flex flex-column min-vh-100">
    <div class="row mx-auto py-3">
      <!-- <b-card
        v-if="!loggedInModel"
        class="m-3 p-5"
        title="Login"
        sub-title="password"
      >
        <b-form ref="authForm" @submit.prevent="logIn()">
          <b-input-group class="mt-5">
            <template #prepend>
              <b-input-group-text
                ><b-icon icon="key"></b-icon
              ></b-input-group-text>
            </template>
            <b-form-input v-model="pwModel" type="password" required />
          </b-input-group>
          <b-button
            class="mt-3 font-weight-bold"
            block
            variant="success"
            type="submit"
          >
            Log In
          </b-button>
        </b-form>
      </b-card> -->
      <b-card class="m-3 p-5" title="Vixen Media" sub-title="Model Search">
        <b-form-input
          class="mt-5"
          v-model="pcModel"
          type="search"
        ></b-form-input>
        <b-button
          class="mt-3 font-weight-bold"
          block
          variant="danger"
          type="submit"
          @click="openPremiumContentPortals"
        >
          Open
        </b-button>
        <b-button
          class="mt-3 font-weight-bold"
          block
          variant="outline-danger"
          @click="openPremiumContentBank"
        >
          Other Sites
        </b-button>
      </b-card>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      loggedInModel: localStorage.pw === "password" ? true : false,
      pwModel: "",
      pcModel: "",
      dfModel: { val: localStorage.lastPostBatch || "", maxLink: 0 },
    };
  },
  mounted() {},
  methods: {
    logIn() {
      if (this.pwModel === "password") {
        localStorage.pw = this.pwModel;
        alert("Welcome!");
        this.$refs.authForm.submit();
      } else {
        alert("Wrong!");
      }
    },
    openPremiumContentPortals() {
      var pcModelKebab = this.pcModel.replace(" ", "-");
      if (pcModelKebab === "") {
        pcModelKebab = "videos";
      } else {
        pcModelKebab = "models/" + pcModelKebab;
      }
      window.open("https://www.vixen.com/" + pcModelKebab, Math.random());
      window.open("https://www.tushy.com/" + pcModelKebab, Math.random());
      window.open("https://www.tushyraw.com/" + pcModelKebab, Math.random());
      window.open("https://www.blacked.com/" + pcModelKebab, Math.random());
      window.open("https://www.blackedraw.com/" + pcModelKebab, Math.random());
      window.open("https://www.deeper.com/" + pcModelKebab, Math.random());
      window.open("https://www.milfy.com/" + pcModelKebab, Math.random());
      window.open("https://www.slayed.com/" + pcModelKebab, Math.random());
    },
    openPremiumContentBank() {
      var pcModelKebab1 = this.pcModel.replace(" ", "-");
      if (pcModelKebab1 === "") {
        pcModelKebab1 = "";
      } else {
        pcModelKebab1 = "stars/" + pcModelKebab1;
      }
      window.open(
        "https://tube.perverzija.com/" + pcModelKebab1,
        Math.random()
      );
      var pcModelKebab2 = this.pcModel.replace(" ", "-");
      if (pcModelKebab2 === "") {
        pcModelKebab2 = "";
      } else {
        pcModelKebab2 = "tag/" + pcModelKebab1;
      }
      window.open("https://porndish.com/" + pcModelKebab2, Math.random());
      var pcModelKebab3 = this.pcModel.replace(" ", "-");
      if (pcModelKebab3 === "") {
        pcModelKebab3 = "";
      } else {
        pcModelKebab3 = "tag/" + pcModelKebab3 + ".html";
      }
      window.open("https://sxyprn.com/" + pcModelKebab3, Math.random());
      this.pcModel = "";
    },
    postIdMax() {
      return parseInt(this.dfModel.val) + parseInt(this.dfModel.maxLink);
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

  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
