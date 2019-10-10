<template>
  <div class="home">
    <Task1 />
  </div>
</template>

<script>
// @ is an alias to /src
import Task1 from "@/components/Task1.vue";

export default {
  beforeMount() {
    this.delay(1800);
  },
  name: "home",
  components: {
    Task1
  },
  methods: {
    delay(ms) {
      const startPoint = new Date().getTime();
      while (new Date().getTime() - startPoint <= ms) {
        /* wait */
      }
    }
  }
};
</script>

<style>
.home {
  height: 100%;
}
</style>
