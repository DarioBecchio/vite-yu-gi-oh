<script>
export default {
  name: "FilterElement",
  props: {
    type: String,
  },
};
</script>
<template>
  <option :value="type" :key="type">
    {{ type }}
  </option>
</template>
<style></style>
