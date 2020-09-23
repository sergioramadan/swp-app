<template>
  <div>
    <ul v-if="list.length">
      <Film
        v-for="element in list"
        :key="element"
        :apiUrl="element"
      />
    </ul>
    <span v-else>No results</span>
  </div>
</template>

<script>
import Film from "./Film";

export default {
  name: "FilmList",
  components: {
    Film
  },
  props: {
    list: {
      type: Array
    }
  }
}
</script>