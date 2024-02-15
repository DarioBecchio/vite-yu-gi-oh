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
      characters: [],
      types: [],
      selectedTypes: "",
    };
  },
  methods: {
    chooseTypes() {
      axios
        .get(this.base_api_url)
        .then((response) => {
          this.characters = response.data.data;
          this.characters.forEach((element) => {
            if (element.archetype) {
              const type = element.archetype;
              if (!this.types.includes(type)) {
                this.types.push(type);
              }
            }
          });
        })
        .catch((error) => {
          console.error(error.message);
        });
    },
  },
  computed: {},
  mounted() {
    this.chooseTypes();
  },
};
</script>
<template>
  <main>
    <div class="container">
      <div class="filters">
        <select
          v-model="selectedTypes"
          @change="chooseTypes()"
          name="archetype"
          id=""
        >
          <FilterElement
            v-for="(option, index) in types"
            :key="index"
            :type="option"
          ></FilterElement>
        </select>
      </div>
      <div class="row">
        <CardElement
          v-for="character in characters"
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
