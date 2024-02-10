<script>
import axios from "axios";
export default {
  name: "App",
  data() {
    return {
      base_api_url: "https://db.ygoprodeck.com/api/v7/cardinfo.php",
    };
  },
  mounted() {
    axios.get("").then((response) => {
      console.log(response);
    });
  },
};
</script>

<template>
  <AppHeader></AppHeader>
  <AppMain></AppMain>
  <AppFooter></AppFooter>
</template>

<style></style>
