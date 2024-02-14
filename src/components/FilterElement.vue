<script>
export default {
  name: "FilterElement",
  props: {
    character: Object,
  },
};
</script>
<template>
  <select name="archetype" id="">
    <option :value="character.archetype">
      {{ character.archetype }}
    </option>
  </select>
</template>
<style></style>
