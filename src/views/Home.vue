<template>
  <div class="home">
    <Loader :isLoading="isLoading" />
    <div v-if="!isLoading">
      <Task1 />
      <Task2 />
      <Task3 />
      <Task4 />
      <Footer />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Loader from "@/components/Loader.vue";
import Task1 from "@/components/Task1.vue";
import Task2 from "@/components/Task2.vue";
import Task3 from "@/components/Task3.vue";
import Task4 from "@/components/Task4.vue";
import Footer from "@/components/Footer.vue";

export default {
  name: "home",
  components: {
    Loader,
    Task1,
    Task2,
    Task3,
    Task4,
    Footer
  },
  data() {
    return { isLoading: true };
  },
  mounted() {
    setTimeout(() => {
      this.isLoading = false;
    }, 2200);
  }
};
</script>

<style>
.home {
  height: 100%;
}
</style>
