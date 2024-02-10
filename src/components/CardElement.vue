<script>
export default {
  name: "CardElement",
  props: {
    character: Object,
  },
};
</script>
<template>
  <div
    class="col-12 col-sm-6 col-lg-4"
    v-for="character in characters.data"
    :key="character.id + '_character'"
  >
    <div class="card">
      <img src="" alt="" />
      <h3>{{ character.name }}</h3>
      <p>{{ character.archetype }}</p>
    </div>
  </div>
</template>
<style></style>
