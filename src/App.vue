<template>
  <div id="app">
    <Loader :isLoading="isLoading"/>
    <main v-if="!isLoading">
      <router-view />
    </main>
  </div>
</template>

<script>
import Loader from "@/components/Loader.vue";
export default {
    name: "App",
  components: {
    Loader
  },
    data() {
    return { isLoading: true };
  },
  mounted() {
    setTimeout(() => {
      this.isLoading = false;
    }, 3000);
  }
}
</script>
<style>
body {
  margin: 0;
}
@import url("https://fonts.googleapis.com/css?family=Montserrat:400,600&display=swap");
#app {
  font-family: "Montserrat", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #5c5c5c;
  line-height: 30px;
}
/* #app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
} */
/* #nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
} */
</style>
