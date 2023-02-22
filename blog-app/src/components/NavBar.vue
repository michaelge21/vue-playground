<template>
  <ul>
    <li></li>
    <li>Portfolio</li>
    <li>About</li>
    <li>Resume</li>
    <li>Contact</li>
  </ul>
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style scoped>
ul {
  display: flex;
  place-items: center;
  flex-flow: row wrap;

  list-style: none;
}

li:first-child {
  margin-right: auto;
  background-image: url("../assets/betterMichaelReducedSize.jpg");
  background-repeat: no-repeat;
  background-size: contain;
  width: 100px;
  height: 100px;
}

li {
  margin: 10px 20px 0 20px;
  font-size: calc(1vw + 1vh + 0.5rem);
}
</style>
