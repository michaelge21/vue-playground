<template>
  <main>
    <section>
      <Child :age="10" :name="'Bruh...'" :yesProp="true"></Child>
      <Child :age="100" :name="'second name'"></Child>
    </section>
  </main>
</template>

<script>
import Child from "./components/Child.vue";

export default {
  name: "App",
  components: {
    Child,
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

    display: flex;
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
