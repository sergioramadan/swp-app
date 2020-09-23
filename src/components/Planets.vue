<template>
  <v-container>
    <Sort @updateOrder="updateOrder" />
    <PlanetList :list="sortedPlanets" />
  </v-container>
</template>

<script>
import axios from "axios";
import { ASC, DSC, NONE } from "@/helpers/SortOptions";
import PlanetList from "@/components/PlanetList";
import Sort from "@/components/Sort";

export default {
  name: "SWPlanets",
  components: {
    PlanetList,
    Sort
  },
  data() {
    return {
      planets: [],
      sortType: NONE
    };
  },
  computed: {
    sortedPlanets() {
      if (this.sortType === ASC) {
        return this.ascSort(this.planets);
      }
      if (this.sortType === DSC) {
        return this.dscSort(this.planets);
      }
      return this.planets;
    }
  },
  methods: {
    ascSort(planets) {
      const planetsClone = planets.slice(0);
      return planetsClone.sort((first, second) => {
        const firstName = first.name.toLowerCase();
        const secondName = second.name.toLowerCase();
        return firstName < secondName ? -1 : firstName > secondName ? 1 : 0;
      });
    },
    dscSort(planets) {
      const planetsClone = planets.slice(0);
      return planetsClone.sort((first, second) => {
        const firstName = first.name.toLowerCase();
        const secondName = second.name.toLowerCase();
        return firstName > secondName ? -1 : firstName < secondName ? 1 : 0;
      })
    },
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
    },
    updateOrder(sort) {
      this.sortType = sort;
    }
  },
  mounted() {
    this.getPlanetList('https://swapi.dev/api/planets/');
  }
}
</script>

<style scoped>

</style>