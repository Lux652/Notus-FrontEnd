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
.loader {
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

.fadeout {
  -webkit-animation: fadeout 3s linear forwards;
  animation: fadeout 3s linear forwards;
}

@keyframes fadeout {
  to {
    opacity: 0;
    visibility: hidden;
  }
}
</style>