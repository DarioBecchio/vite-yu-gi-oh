<script>
import axios from "axios";
import CardElement from "./CardElement.vue";
import FilterElement from "./FilterElement.vue";
export default {
  name: "AppMain",
  components: { CardElement, FilterElement },
  data() {
    return {
      base_api_url:
        "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0",
      characters: " ",
    };
  },
  methods: {},
  computed: {},
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
      <div class="filters">
        <FilterElement
          v-for="character in characters.data"
          :key="character.id + '_character'"
          :character="character"
        ></FilterElement>
      </div>
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
main {
  background-color: orange;
  & > container {
    background-color: white;
  }
}
</style>
