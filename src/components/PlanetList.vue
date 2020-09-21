<template>
  <v-row no-gutters>
    <v-col
      v-for="element in list"
      :key="element.name"
      cols="12"
      sm="4"
    >
      <Planet :info="element" />
    </v-col>
  </v-row>
</template>

<script>
import Planet from "./Planet";

export default {
  name: "PlanetList",
  components: {
    Planet
  },
  props: {
    list: {
      type: Array
    }
  }
}
</script>