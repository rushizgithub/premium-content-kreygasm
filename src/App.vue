<template>
  <div id="app" class="d-flex min-vh-100">
    <div class="mx-auto mt-5">
      <b-card
        class="p-5"
        title="Premium Content"
        sub-title="Search for premium content Kreygasm"
      >
        <b-form class="mt-5" @submit="openKreygasmPortals">
          <b-form-input v-model="inputModel" type="search"></b-form-input>
          <b-button
            class="mt-3 font-weight-bold"
            block
            variant="danger"
            type="submit"
          >
            DAVAI
          </b-button>
        </b-form>
        <b-button
          class="mt-3 font-weight-bold"
          block
          variant="outline-danger"
          @click="openKreygasmBank"
        >
          Kreygasm Bank (DS)
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
      inputModel: "",
    };
  },
  methods: {
    openKreygasmPortals() {
      var inputModelKebab = this.inputModel.replace(" ", "-");
      if (inputModelKebab === "") {
        inputModelKebab = "videos";
      }
      window.open("https://www.vixen.com/" + inputModelKebab, "_blank");
      window.open("https://www.tushy.com/" + inputModelKebab, "_blank");
      window.open("https://www.blacked.com/" + inputModelKebab, "_blank");
      window.open("https://www.tushyraw.com/" + inputModelKebab, "_blank");
      window.open("https://www.blackedraw.com/" + inputModelKebab, "_blank");
      window.open("https://www.deeper.com/" + inputModelKebab, "_blank");
    },
    openKreygasmBank() {
      window.open("https://www.daftsex.com/video/" + this.inputModel, "_blank");
      this.inputModel = "";
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
