<template>
  <div class="card brew-list">
    <div class="card-header text-center">Breweries</div>
    <ul class="list-group list-group-flush">
      <li
        class="list-group-item"
        v-for="(brew, index) in brews"
        :key="index"
      >{{brew.name}}, {{brew.state}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "BrewList",
  props: {
    brews: Array,
  },
};
</script>

<style lang="scss" scoped>
.brew-list {
  overflow-y: scroll;
  // overflow: hidden;
  height: 94vh;
  li {
    &:hover {
      background-color: darkgrey;
    }
  }
}
</style>