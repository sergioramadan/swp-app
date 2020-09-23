<template>
  <li>{{residentData.name}}</li>
</template>

<script>
import axios from "axios";

export default {
  name: "Resident",
  props: {
    apiUrl: {
      type: String
    }
  },
  data() {
    return {
      residentData: {}
    }
  },
  mounted(){
    axios.get(this.apiUrl)
      .then(({data}) => this.residentData = data)
      .catch((err) => (console.log(err)))
  }
}
</script>