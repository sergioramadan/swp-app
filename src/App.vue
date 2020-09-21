<template>
  <v-app>
    <v-app-bar
      app
      color="secondary"
      dark
    >
      <div class="d-flex align-center">
        <h1>Star Wars Planets app</h1>
      </div>
    </v-app-bar>

    <v-main>
      <SWPlanets/>
    </v-main>
  </v-app>
</template>

<script>
import SWPlanets from './components/SWPlanets.vue';

export default {
  name: 'App',
  components: {
    SWPlanets
  }
};
</script>
