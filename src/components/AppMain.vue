<script>
import axios from "axios";
export default {
  name: "AppMain",
  data() {
    return {
      base_api_url:
        "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0",
      characters: " ",
    };
  },
  mounted() {
    axios
      .get(this.base_api_url)
      .then((response) => {
        console.log(this);
        this.characters = response.data;
      })
      .catch((error) => {
        console.error(error.message);
      });
  },
};
</script>
<template>
  <main>
    <div class="container">
      <div class="row">
        <div
          class="col-5 cards"
          v-for="character in characters.data"
          :key="id + '_character'"
        >
          <img :src="character.card_images" alt="" />
          {{ character.name }}
        </div>
      </div>
    </div>
  </main>
</template>
<style></style>
