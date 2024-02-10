<script>
import axios from "axios";
import CardElement from "./CardElement.vue";
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
  components: { CardElement },
};
</script>
<template>
  <main>
    <div class="container">
      <div class="row">
        <CardElement
          v-for="character in characters.data"
          :key="character.id + '_character'"
          :character="character"
        ></CardElement>
      </div>
    </div>
  </main>
</template>
<style>
.card {
  background-color: orange;
  & > img {
    width: 100%;
  }
}
</style>
