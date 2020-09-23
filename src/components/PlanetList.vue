<template>
  <v-expansion-panels>
    <Planet
      v-for="element in list"
      :key="element.name"
      :info="element"
    />
  </v-expansion-panels>
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