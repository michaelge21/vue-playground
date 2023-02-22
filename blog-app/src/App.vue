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
      mouseX: 0,
      mouseY: 0,
      red: 0,
      green: 170,
      blue: 0,
      rgb: "rgb(200,200,200)",
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
  methods: {
    mouseEnter(event) {
      this.mouseX = event.pageX;
      this.mouseY = event.pageY;
      this.convertToRGB();
    },
    mouseMove(event) {
      this.mouseX = event.pageX;
      this.mouseY = event.pageY;
      this.convertToRGB();
    },
    mouseLeave(event) {
      this.mouseX = event.pageX;
      this.mouseY = event.pageY;
      this.convertToRGB();
    },

    convertToRed() {
      this.red = Math.round((this.mouseX / window.innerWidth) * 255);
      return this.red;
    },

    convertToGreen() {
      this.green = Math.round((this.mouseY / window.innerHeight) * 255);
      return this.green;
    },

    convertToBlue() {
      this.blue = Math.round(
        ((this.mouseY + this.mouseX) / window.innerWidth) * 255
      );
      return this.blue;
    },

    convertToRGB() {
      this.red = this.convertToRed();
      this.blue = this.convertToBlue();

      let l1 = 0.2126 * this.red + 0.7152 * this.green + 0.0722 * this.blue;
      let l2 = 1;
      let ratio = (l1 + 0.05) / (l2 + 0.05);
      if (ratio < 4.5) {
        this.blue = Math.round(
          (4.5 * (l2 + 0.05) - 0.05 - 0.2126 * this.red - 0.0722 * this.green) /
            0.7152
        );
      }
      this.rgb = "rgb(" + this.red + ", " + this.green + ", " + this.blue + ")";
    },
  },
};
</script>

<template>
  <header><NavBar></NavBar></header>
  <main>
    <section
      class="hero"
      @mouseenter="(event) => mouseEnter(event)"
      @mousemove="(event) => mouseMove(event)"
      @mouseleave="(event) => mouseLeave(event)"
      :style="{ boxShadow: `0 0 5px 4px ${this.rgb}` }"
    >
      <h1>on a journey to define social impact.</h1>
      <p>
        <span :style="{ color: `rgb(${this.red},${this.green},0)` }"
          >i make websites.</span
        >
        <span :style="{ color: `rgb(0,${this.green},${this.blue})` }">
          i build orgs.</span
        >
      </p>
      <p :style="{ color: rgb }">i mix the two whenever i can.</p>
    </section>

    <section class="blogIntro">
      <h2>i write whenever i'm not dancing or coding!</h2>
      <p>
        looking for something else? please use the navbar to zip onto the next
        destination. :)
      </p>
    </section>

    <section class="blogContainer">
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

<style lang="scss" scoped>
main {
  margin-top: 10vh;
  text-align: center;
}
.hero > h1 {
  font-size: calc(1.2vh + 1.2vw + 1rem);
}
.hero > p {
  font-size: calc(0.8vh + 0.8vw + 0.5rem);
  font-weight: 500;

  margin: 2vh 0;
}

.hero {
  padding: 7vh 0;
  margin: 0 2vw;
  border-radius: 40px;
  transition: all 0.15s;

  &:hover {
    animation-name: borderRadiusBounce;
    animation-duration: 0.4s;
    animation-timing-function: ease-in-out;
  }

  @keyframes borderRadiusBounce {
    20% {
      border-radius: 36px;
    }

    50% {
      border-radius: 43px;
    }

    70% {
      border-radius: 39px;
    }
    90% {
      border-radius: 41px;
    }
    100% {
      border-radius: 40px;
    }
  }
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
