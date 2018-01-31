<template>
  <header id="TheHeader">
    <img src="../../static/g-dino.png" alt="Dinosaur Logo" />
  </header>
</template>

<script>
export default {
  name: 'TheHeader'
};
</script>

<style scoped>
header {
  grid-row: 1 / 2;
  display: grid;
  grid-template-columns: 25% 50% 15%;
  grid-template-rows: 50% 50%;
  padding-top: 10px;
}

img {
  grid-row: 1/3;
  grid-column: 1/2;
  height: 100px;
  width: auto;
}

h1 {
  grid-row: 1/2;
  grid-column: 2/3;
  margin: 0;
  color: #c261cc;
  font-family: serif;
}
</style>
