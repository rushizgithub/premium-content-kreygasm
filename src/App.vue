<template>
  <div id="app" class="d-flex flex-column min-vh-100">
    <div class="row mx-auto py-3">
      <b-card
        class="m-3 p-5"
        title="Premium Content"
        sub-title="Search for premium content Kreygasm"
      >
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
          DAVAI
        </b-button>
        <b-button
          class="mt-3 font-weight-bold"
          block
          variant="outline-danger"
          @click="openPremiumContentBank"
        >
          Kreygasm Bank (DS)
        </b-button>
      </b-card>
      <b-card
        class="m-3 p-5"
        title="Deepfakes Yoinker"
        sub-title="TriHard Yoink the Deepfakes "
      >
        <b-form @submit.prevent="openDeepfakesBank">
          <b-input-group prepend="Start at:" class="mt-5">
            <b-form-input
              v-model="dfModel.val"
              type="number"
              min="0"
              required
            />
          </b-input-group>
          <b-input-group prepend="Max Link:" class="mt-3">
            <b-form-input
              v-model="dfModel.maxLink"
              type="number"
              min="0"
              max="20"
              required
            />
          </b-input-group>
          <b-alert class="mt-3" :show="dfModel.val > 0" variant="info">
            From
            <b>{{ dfModel.val }}</b>
            To
            <b>{{ postIdMax() }}</b>
          </b-alert>
          <b-button
            class="mt-3 font-weight-bold"
            block
            variant="success"
            type="submit"
          >
            YOINK EM ALL
          </b-button>
        </b-form>
      </b-card>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      pcModel: "",
      dfModel: { val: "", maxLink: 0 },
    };
  },
  methods: {
    openPremiumContentPortals() {
      var pcModelKebab = this.pcModel.replace(" ", "-");
      if (pcModelKebab === "") {
        pcModelKebab = "videos";
      }
      window.open("https://www.vixen.com/" + pcModelKebab, Math.random());
      window.open("https://www.tushy.com/" + pcModelKebab, Math.random());
      window.open("https://www.blacked.com/" + pcModelKebab, Math.random());
      window.open("https://www.tushyraw.com/" + pcModelKebab, Math.random());
      window.open("https://www.blackedraw.com/" + pcModelKebab, Math.random());
      window.open("https://www.deeper.com/" + pcModelKebab, Math.random());
    },
    openPremiumContentBank() {
      window.open(
        "https://www.daftsex.com/video/" + this.pcModel,
        Math.random()
      );
      this.pcModel = "";
    },
    postIdMax() {
      return parseInt(this.dfModel.val) + parseInt(this.dfModel.maxLink);
    },
    openDeepfakesBank() {
      var dfMin = this.dfModel.val;
      var dfMax = this.postIdMax();

      for (let postId = dfMin; postId <= dfMax; postId++) {
        window.open("https://fan-topia.com/post/" + postId, postId);
      }
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