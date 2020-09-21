<template>
  <v-container>
    <PlanetList :list="sortedPlanets" />
  </v-container>
</template>

<script>
import axios from "axios";
import PlanetList from "./PlanetList";

export default {
  name: "SWPlanets",
  components: {
    PlanetList
  },
  data() {
    return {
      planets: [],
      sortType: ''
    };
  },
  computed: {
    sortedPlanets() {
      return this.planets
    }
  },
  methods: {
    getPlanetList(url = null) {
      axios
        .get(url)
          .then(({data}) => {
            const {results, next} = data;
            this.planets = [...this.planets, ...results];
            if (next)
              this.getPlanetList(next);
          })
          .catch(err => console.log(err))
    }
  },
  mounted() {
    this.getPlanetList('https://swapi.dev/api/planets/');
  }
}
</script>

<style scoped>

</style>