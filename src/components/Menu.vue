<template>
  <transition name="fade">
    <div class="navbar" v-if="model">
      <img class="notus-logo" src="../assets/Notus-logo-meni.svg" alt />
          <div class="btn-menu">
      <p>Exit</p>
      <button @click.prevent="$emit('toggle-menu', false);">
      <img src="../assets/notus-meni-close.svg" alt=""></button>
    </div>
      <ul class="list">
        <!-- <li class="list-item"><a href="/home">Home</a></li>
        <li class="list-item"><a href="/profile">Profile</a></li>
        <li class="list-item"><a href="/about">About</a></li>
        <li class="list-item"><a href="/pricing">Pricing</a></li>-->
        <!-- <li class="list-item">
          <a href="#" @click.prevent="$emit('toggle-menu', false);">Cerrar</a>
        </li> -->
        <router-link class="list-item" to="#task3"><b>TASK 3</b></router-link> 
        <li class="list-item"><a @click="scrollMeTo('task3')"><b>TASK 3</b></a></li>
        <li class="list-item"><a href=""><b>TASK 4</b></a></li>
        <li class="list-item"><a href=""><b>TASK 5</b></a></li>
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
  background-color:#F89D36;
  position: absolute;
  height: 100vh;
  min-width: 2000px;
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
router-link{
    text-decoration: none;
}
.list-item > b {
  color: white;
  font-size:60px;
  text-decoration: none;
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
</style>
