<script>
export default {
  name: "CardElement",
  props: {
    character: Object,
  },
};
</script>
<template>
  <div class="col-12 col-sm-6 col-lg-5 col-xl-3">
    <div class="card">
      <img :src="character.card_images[0].image_url_small" alt="" />
      <h3>{{ character.name }}</h3>
      <p>{{ character.archetype || character.type }}</p>
    </div>
  </div>
</template>
<style scoped>
.card {
  background-color: orange;
  text-align: center;
  & > img {
    width: 100%;
  }
  & h3 {
    color: white;
    font-weight: 600;
  }
  & p {
    color: black;
  }
}
</style>
