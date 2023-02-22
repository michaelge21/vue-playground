<script>
import NavBar from "./components/NavBar.vue";
import BlogOutline from "./components/BlogOutline.vue";

export default {
  name: "App",
  components: {
    NavBar,
    BlogOutline,
  },
  data() {
    return {
      postInfo: [
        {
          id: 1,
          title: "Asian Mental Health: Organizing Conversations",
          desc: "Breaking News: we, the youth, are noticing that maybe being stereotyped as perfectionists isn't good for us.",
          url: "/src/assets/betterMichaelReducedSize.jpg",
          altText: "alt1",
          destination: "#",
        },
        {
          id: 2,
          title: "Zoom University",
          desc: "Published by WashU's Center for Teaching and Learning. ",
          url: "/src/assets/instructormeme.jpg",
          altText: "alt2",
          destination:
            "https://ctl.wustl.edu/zoom-university-students-and-instructors-on-pandemic-learning/",
        },
        {
          id: 3,
          title: "n00b perspectives: Learning Curves",
          desc: "Some thoughts for fellow front-end learners, especially self-taught friends.",
          url: "/src/assets/betterMichaelReducedSize.jpg",
          altText: "alt3",
          destination: "#",
        },
        {
          id: 4,
          title: "n00b perspectives: Feedback",
          desc: "Feedback is a huge part of Agile. Classrooms and EdPsych have been doing it for centuries... so what can we glean from our educators?",
          url: "/src/assets/betterMichaelReducedSize.jpg",
          altText: "alt3",
          destination: "#",
        },
      ],
    };
  },
};
</script>

<template>
  <header><NavBar></NavBar></header>
  <main>
    <h1>hey! i'm michael ge.</h1>
    <p><span>i make websites.</span> i build orgs.</p>
    <p>i mix the two whenever i can.</p>

    <section class="blogIntro">
      <h2>i write whenever i'm not dancing or coding!</h2>
      <p>
        looking for something else? please use the navbar to zip onto the next
        destination. :)
      </p>
    </section>

    <section class="blogContainer">
      <!-- <div>
        <BlogPost title="testing" desc="description"></BlogPost>
      </div>
      <div>
        <BlogPost
          title="testing a second"
          desc="another description"
        ></BlogPost>
      </div> -->

      <BlogOutline
        v-for="post in postInfo"
        :key="post.id"
        :title="post.title"
        :desc="post.desc"
        :url="post.url"
        :destination="post.destination"
      ></BlogOutline>
    </section>
  </main>
</template>

<style scoped>
main {
  margin-top: 10vh;
  text-align: center;
}
main > h1 {
  font-size: calc(1.2vh + 1.2vw + 1rem);
}
main > p {
  font-size: calc(0.8vh + 0.8vw + 0.5rem);
  font-weight: 500;

  margin: 2vh 0;
}
h1 + p {
  color: rgb(0, 0, 255);
}
h1 + p span {
  color: rgb(255, 255, 0);
}
h1 + p + p {
  color: rgb(0, 128, 0);
}

main > .blogIntro {
  margin-top: 10vh;
}

.blogContainer {
  display: flex;
  justify-content: center;
  flex-flow: row wrap;

  width: 100%;

  gap: calc(1vw + 2vh + 3rem);
}

.blogContainer > * {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s all;
  flex: 1 400px;
  margin: 10px 20px;
}

.blogContainer > *:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}
</style>

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
