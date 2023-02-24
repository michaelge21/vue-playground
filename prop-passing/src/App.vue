<template>
  <main>
    <section>
      <Child :age="10" :name="'xX_broMeister_Xx'" :yesProp="true"></Child>
      <Child :age="100" :name="'second name'"></Child>
    </section>

    <section>
      <StyleChild
        :color="'red'"
        :fontSize="40"
        :disableClick="true"
      ></StyleChild>
    </section>

    <section>
      <NavBar :disableLink="3"></NavBar>
    </section>
  </main>
</template>

<script>
import Child from "./components/Child.vue";
import StyleChild from "./components/StyleChild.vue";
import NavBar from "./components/NavBar.vue";

export default {
  name: "App",
  components: {
    Child,
    StyleChild,
    NavBar,
  },
};
</script>

<style lang="scss" scoped>
main {
  section {
    max-width: 1024px;
    background-color: #222222;
    color: white;
    padding: 5vw;
    margin: 10px;

    display: flex;
    flex-flow: row wrap;
    justify-content: space-around;

    section {
      flex-basis: 300px;

      display: flex;
      place-items: center;
      gap: 20px;
    }
  }
}
</style>
