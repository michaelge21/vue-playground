<template>
  <h2 :style="{ color: this.color, fontSize: `${this.fontSize}px` }">
    hey! let's try this.
  </h2>
  <p>
    <a href="#" :class="{ notClickable: disableClick }"
      >let's see if class-bindings work.</a
    >
  </p>
</template>

<script>
export default {
  name: "StyleChild",
  data() {
    return {};
  },
  props: {
    color: String,
    fontSize: {
      type: Number,
      default() {
        return 40;
      },
    },
    disableClick: {
      type: Boolean,
      default() {
        return false;
      },
    },
  },
};
</script>

<style lang="scss" scoped>
.notClickable {
  pointer-events: none;
  color: pink;
}
</style>
