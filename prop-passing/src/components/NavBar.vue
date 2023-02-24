<template>
  <nav>
    <ul>
      <li>
        <a href="#" :class="{ disableClick: this.disableLink == 1 }">link</a>
      </li>
      <li>
        <a href="#" :class="{ disableClick: this.disableLink == 2 }"
          >2nd link</a
        >
      </li>
      <li>
        <a href="#" :class="{ disableClick: this.disableLink == 3 }"
          >3rd link</a
        >
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
  data() {
    return {
      //   disableLink: "bruh",
    };
  },
  props: {
    disableLink: {
      type: Number,
      default() {
        return 1;
      },
    },
  },
};
</script>

<style lang="scss" scoped>
ul {
  display: flex;
  justify-content: center;
  align-items: center;
  list-style: none;
  gap: 40px;

  li {
    a {
      text-decoration: overline;
      text-decoration-thickness: 2px;
    }
    a.disableClick {
      pointer-events: none;
      color: pink;
      text-decoration: none;
    }
  }
}
</style>
