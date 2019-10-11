<template>
  <transition name="fade">
    <div class="navbar" v-if="model">
      <img class="notus-logo" src="../assets/Notus-logo-meni.svg" alt />
      <div class="btn-menu">
        <p>Exit</p>
        <button @click.prevent="$emit('toggle-menu', false)">
          <img src="../assets/notus-meni-close.svg" alt />
        </button>
      </div>
      <ul class="list">
        <router-link class="list-item" to="#task3">
          <b>TASK 3</b>
        </router-link>
        <router-link class="list-item" to="#task4">
          <b>TASK 4</b>
        </router-link>
        <router-link class="list-item" to="#task5">
          <b>TASK 5</b>
        </router-link>
      </ul>
    </div>
  </transition>
</template>

<script>
export default {
  name: "Menu",
  data() {
    return {};
  },
  props: {
    model: {
      type: Boolean,
      default: false
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.navbar {
  background-color: #f89d36;
  position: absolute;
  height: 100vh;
  min-width: 100%;
  left: 0;
  top: 0;
  z-index: 999;
}

.list {
  font-size: 20px;
  list-style: none;
  margin: 2px 0 0 0;
  padding-top: 20px;
  position: absolute;
  z-index: 2;
  left: 15%;
  top: 35%;
}

.list-item {
  color: white;
  margin: 1px;
  padding: 15px;
}
a {
  text-decoration: none;
}
.list-item > b {
  color: white;
  font-size: 60px;
  display: block;
  margin-top: 20px;
}

.fade-enter-active,
.fade-leave-active {
  transition: left 0.2s ease-in-out;
}
.fade-enter,
.fade-leave-to {
  left: -200px;
}

.notus-logo {
  position: absolute;
  z-index: 2;
  left: 47.5%;
  margin-left: -50px;
  top: 0;
  margin-top: 40px;
}


@media (min-width: 1281px) {

  .notus-logo {
    position: absolute;
    z-index: 2;
    left: 50%;
    margin-left: -50px;
    top: 0;
    margin-top: 40px;
  }
}


@media (min-width: 768px) and (max-width: 1024px) {


  .notus-logo {
    width: 10%;
    margin-left: -25px;
  }
  .list {
  font-size: 20px;
  left: 10%;
  margin-top:-10%;
}


.list-item > b {
  font-size: 50px;
}

}

@media (min-width: 481px) and (max-width: 767px) {


  .notus-logo {
    width: 8%;
    margin-left: -15px;
  }
  .list {
  font-size: 20px;
  left: 10%;
  margin-top:-40%;
}

.list-item > b {
  font-size: 40px;
}


}

@media (max-width: 480px) {
    .notus-logo {
    width: 9%;
    margin-left: -15px;
  }
  .list {
  font-size: 20px;
  left: 10%;
  margin-top:-50%;
}

.list-item > b {
  font-size: 25px;
}
}
</style>
