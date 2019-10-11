<template>
  <div class="task3" id="task4">
    <Carousel :items="items" :limit="showLimit" />
  </div>
</template>

<script>
import Carousel from "@/components/Carousel.vue";

export default {
  name: "Task3",
  components: {
    Carousel
  },
  data() {
    return {
      window: {
        width: 0
      },
      showLimit: 0,
      items: [
        { id: 0, path: require("../assets/notus-task3-img1.jpg") },
        { id: 1, path: require("../assets/notus-task3-img2.jpg") },
        { id: 2, path: require("../assets/notus-task3-img3.jpg") },
        { id: 3, path: require("../assets/notus-task3-img4.jpg") }
      ]
    };
  },
  created() {
    window.addEventListener("resize", this.handleResize);
    this.handleResize();
  },
  destroyed() {
    window.removeEventListener("resize", this.handleResize);
  },
  methods: {
    handleResize() {
      this.window.width = window.innerWidth;
      if (this.window.width >= 1281) {
        this.showLimit = 3;
      } else if (this.window.width >= 1025 && this.window.width <= 1280) {
        this.showLimit = 2;
      } else {
        this.showLimit = 1;
      }
    }
  }
};
</script>

<style>
.limit {
  margin: 0 auto;
  width: 20px;
}
.task3 {
  margin-top: 10%;
  height: 100vh;
}
</style>
