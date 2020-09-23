<template>
  <v-col cols="12" sm="4" class="planet-info">
    <h4>{{title}}</h4>
    <slot></slot>
  </v-col>
</template>

<script>
export default {
  name: "PlanetInfo",
  props: {
    title: {
      type: String
    }
  }
}
</script>

<style scoped>
  .planet-info {
    margin: 5px 0;
  }
</style>