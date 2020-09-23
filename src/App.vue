<template>
  <v-app>
    <v-app-bar
      app
      color="secondary"
      dark
    >
      <img
        class="logo"
        alt="Star Wars Planets app logo"
        src="./assets/star-wars-logo.png"
      />
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
import SWPlanets from './components/Planets.vue';

export default {
  name: 'App',
  components: {
    SWPlanets
  }
};
</script>

<style>
  h1 {
    vertical-align: center;
  }

  img.logo {
    display: inline-block;
    height: 50px;
    margin: 0 10px;
  }
</style>
