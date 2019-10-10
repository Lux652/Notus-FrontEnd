<template>
  <div class="home">
    <Task1 />
	<Task2/>
  </div>
</template>

<script>
// @ is an alias to /src
import Task1 from "@/components/Task1.vue";
import Task2 from "@/components/Task2.vue";

export default {
  beforeMount() {
    this.delay(3900);
  },
  name: "home",
  components: {
    Task1,
    Task2
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
