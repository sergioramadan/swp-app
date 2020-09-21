<template>
  <v-card 
    class="pa-2 planet-card"
    outlined
    tile>
    <h2 @click="toggleData">{{info.name}}</h2>
    <div v-if="showData">
      <h3>Planet Data</h3>
      <h4>Rotation Period</h4>
      {{info.rotation_period}}
      <h4>Orbital Period</h4>
      {{info.orbital_period}}
      <h4>Diameter</h4>
      {{info.diameter}}
      <h4>Climate</h4>
      {{info.climate}}
      <h4>Gravity</h4>
      {{info.gravity}}
      <h4>Population</h4>
      {{info.population}}
      <ResidentList :list="info.residents"/>
      <FilmList :list="info.films" />
    </div>
  </v-card>
</template>

<script>
import FilmList from "./FilmList";
import ResidentList from "./ResidentList";

export default {
  name: 'Planet',
  components: {
    FilmList,
    ResidentList
  },
  props: {
    info: {
      type: Object
    }
  },
  data() {
    return {
      showData: false
    }
  },
  methods: {
    toggleData() {
      this.showData = !this.showData
    }
  },
}
</script>

<style scoped>
  .planet-card {
    margin: 5px;
    padding: 10px;
  }
  span {
    text-transform: capitalize;
  }
</style>