<template>
  <div :class="{loader:true, fadeout: !isLoading}" class="load fade">
    <img src="../assets/Notus-logo-loading.svg" alt />
  </div>
</template>

<script>
export default {
  name: "Loader",
  props: ["isLoading"]
};
</script>

<style>
.load {
  background-color: #081b2f;
  overflow: hidden;
  top: 0;
  left: 0;
  right: 0;
  position: fixed;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
  opacity: 1;
}

.fade {
  -webkit-animation: fadeinout 4s linear forwards;
  animation: fadeinout 4s linear forwards;
}

@keyframes fadeinout {
  0%,
  100% {
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
}
</style>