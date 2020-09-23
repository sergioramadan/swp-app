<template>
  <v-expansion-panel>
    <v-expansion-panel-header>
      <h2>{{info.name}}</h2>
    </v-expansion-panel-header>
    <v-expansion-panel-content>
      <v-row no-gutters>
        <v-col cols="12">
          <h3>Planet Data</h3>
        </v-col>
        <PlanetInfo title="Rotation Period">
          {{info.rotation_period}}
        </PlanetInfo>
        <PlanetInfo title="Orbital Period">
          {{info.orbital_period}}
        </PlanetInfo>
        <PlanetInfo title="Diameter">
          {{info.diameter}}
        </PlanetInfo>
        <PlanetInfo title="Climate">
          {{info.climate}}
        </PlanetInfo>
        <PlanetInfo title="Gravity">
          {{info.gravity}}
        </PlanetInfo>
        <PlanetInfo title="Population">
          {{info.population}}
        </PlanetInfo>
        <PlanetInfo title="Residents">
          <ResidentList :list="info.residents" />
        </PlanetInfo>
        <PlanetInfo title="Films">
          <FilmList :list="info.films" />
        </PlanetInfo>
      </v-row>
    </v-expansion-panel-content>
  </v-expansion-panel>
</template>

<script>
import PlanetInfo from "./PlanetInfo";
import FilmList from "./FilmList";
import ResidentList from "./ResidentList";

export default {
  name: 'Planet',
  components: {
    FilmList,
    ResidentList,
    PlanetInfo
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