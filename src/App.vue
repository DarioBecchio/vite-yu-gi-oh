<script>
import axios from "axios";
export default {
  name: "App",
  data() {
    return {
      base_api_url: "",
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
