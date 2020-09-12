<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <h1 class="text-center text-info">Breweries list</h1>
      </div>
    </div>

    <div class="row">
      <div class="col-6">
        <!-- BrewList component -->
        <BrewList :brews="brews" />
      </div>
      <div class="col-6">
        <h2 class="text-center">Right</h2>
        <!-- Map component here -->
        <BrewMap />
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import BrewList from "./BrewList.vue";
import BrewMap from "./BrewMap.vue";

export default {
  components: {
    BrewList,
    BrewMap,
  },
  name: "Brew",
  data() {
    return {
      brews: [],
    };
  },
  mounted() {
    console.log("mounted");
    axios.get("https://api.openbrewerydb.org/breweries").then((res) => {
      let data = res.data;
      console.log(data);
      this.brews = res.data;
    });
  },
};
</script>

<style lang="scss" scoped>
</style>
