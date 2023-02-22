<template>
  <NavBar></NavBar>
</template>

<script>
import NavBar from "../../components/NavBar.vue";

export default {
  name: "Portfolio",
  components: { NavBar },
};
</script>

<style lang="scss" scoped></style>

<style>
*,
::before,
::after {
  box-sizing: border-box;
  font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, sans-serif;
}

p,
h1,
h2,
h3,
h4,
h5,
ul,
li,
main,
body {
  margin: 0;
  padding: 0;
}
</style>
