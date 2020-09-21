<template>
  <div>
    <h4>Residents</h4>
    <div v-if="list.length">
      <Resident
        v-for="element in list"
        :key="element"
        :apiUrl="element"
      />
    </div>
    <span v-else>No results</span>
  </div>
</template>

<script>
import Resident from "./Resident";

export default {
  name: "ResidentList",
  components: {
    Resident
  },
  props: {
    list: {
      type: Array
    }
  }
}
</script>