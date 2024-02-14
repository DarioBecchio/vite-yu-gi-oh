<script>
export default {
  name: "AppHeader",
};
</script>
<template>
  <header>
    <div class="container">
      <div class="logo">
        <img
          src="https://vignette1.wikia.nocookie.net/yugiohenespanol/images/a/aa/Yugioh_anime_logo.jpg/revision/latest?cb=20130310042737&path-prefix=es"
          alt=""
        />
      </div>
      <h2>Yu-Gi-Oh Api</h2>
    </div>
  </header>
</template>
<style>
header {
  background-color: white;
  & > h2 {
    color: black;
    margin: 1rem 0;
  }
  & > .container {
    display: flex;
    align-items: center;
  }
}
.logo {
  height: 100px;
  width: 200px;
}
</style>
