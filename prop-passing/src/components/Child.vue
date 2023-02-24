<template>
  <section>
    <p>{{ age }}</p>
    <p>{{ name }}</p>
    <p>{{ description.favSong }}</p>
    <p>{{ description.favPerson }}</p>
    <p v-if="yesProp">you should only see this if the yesProp is "true"</p>
    <p v-else>you'll see this if yesProp is false</p>
  </section>
</template>

<script>
export default {
  name: "Child",
  props: {
    age: {
      type: Number,
      required: true,
    },
    name: {
      type: String,
    },
    description: {
      type: Object,
      default(theProp) {
        return {
          favSong: "your favorite song goes here!",
          favPerson: "your favorite person goes here!",
        };
      },
    },
    yesProp: {
      type: Boolean,
      default() {
        return false;
      },
    },
  },
};
</script>

<style lang="scss" scoped></style>
