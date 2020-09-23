<template>
  <li>{{filmData.title}}</li>
</template>

<script>
import axios from "axios";

export default {
  name: "Film",
  props: {
    apiUrl: {
      type: String
    }
  },
  data() {
    return {
      filmData: {}
    }
  },
  mounted() {
    axios.get(this.apiUrl)
      .then(({data}) => (this.filmData = data))
      .catch(err => console.log(err));
  }
}
</script>