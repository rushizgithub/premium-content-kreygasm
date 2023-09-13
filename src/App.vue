<template>
  <div id="app" class="d-flex flex-column min-vh-100">
    <div class="row mx-auto py-3">
      <b-card class="m-3 p-5" title="Vixen Media" sub-title="Model Search">
        <b-form-input
          v-model="pcModel"
          class="mt-5"
          type="search"
        ></b-form-input>
        <b-button
          @click="openPremiumContentPortals"
          class="mt-3 font-weight-bold"
          block
          variant="danger"
          type="submit"
          >Open</b-button
        >
        <b-button
          @click="openOtherSites"
          class="mt-3 font-weight-bold"
          block
          variant="outline-danger"
          >Other Sites</b-button
        >
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
    };
  },
  methods: {
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

      this.pcModel = "";
    },
    openOtherSites() {
      const pcModelKebab = this.pcModel.trim().replace(/\s+/g, "-") || "";
      const sites = [
        {
          url: "https://tube.perverzija.com/",
          path: "stars",
        },
        {
          url: "https://porndish.com/",
          path: "tag",
        },
        {
          url: "https://sxyprn.com/",
          path: "tag",
        },
      ];

      sites.forEach((site) => {
        const path = pcModelKebab ? `${site.path}/${pcModelKebab}` : "";
        this.openUrl(`${site.url}${path}`);
      });

      this.pcModel = "";
    },
  },
};
</script>

<style>
/* Dark Theme Styles */
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000; /* Set text color for dark theme */
  background-color: #121212; /* Set background color for dark theme */
  margin-top: 60px;
}

/* Additional dark theme styles for specific elements if needed */
.b-card {
  background-color: #1e1e1e;
  color: #ffffff;
}

/* Add more styles as needed for specific elements */
</style>
