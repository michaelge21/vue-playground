<template>
  <article>
    <a :href="destination" target="_blank"></a>
    <h2>{{ title }}</h2>
    <p>{{ desc }}</p>
    <img :src="url" :alt="altText" />
  </article>
</template>

<script>
export default {
  name: "BlogOutline",
  props: {
    title: String,
    desc: String,
    url: String,
    altText: String,
    destination: String,
  },
};
</script>

<style scoped>
article {
  position: relative;
  background: hsl(207, 30%, 90%);
  color: #333333;
}

article img {
  max-width: 200px;
}

a {
  position: absolute;
  display: block;
  width: 100%;
  height: 100%;
}
</style>
