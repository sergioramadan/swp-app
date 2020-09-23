<template>
  <v-select
    :items="items"
    filled
    label="Sort"
    :value="defaultValue"
    @change="triggerChange"
  ></v-select>
</template>

<script>
import { ASC, DSC, NONE } from "@/helpers/SortOptions";

export default {
  data: () => ({
    defaultValue: NONE,
    items: [NONE, ASC, DSC]
  }),
  methods: {
    triggerChange(value) {
      this.$emit("updateOrder", value);
    }
  }
}
</script>