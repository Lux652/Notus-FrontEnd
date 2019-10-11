<template>
  <transition-group name="fade" mode="out-in" tag="div" id="slides">
    <div class="slideContainer" :key="image.id">
      <div class="slideImg" :style="setBackgroundImage">
        <div class="layer"></div>
      </div>
    </div>
  </transition-group>
</template>

<script>
export default {
  props: ["image"],
  computed: {
    setBackgroundImage() {
      return { background: `url(${this.image.path})` };
    }
  }
};
</script>

<style>
.layer {
  background-color: rgba(8, 27, 47, 0.7);
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
#slides .slideContainer {
  height: 100vh;
  width: 100%;
}
#slides .slideImg {
  height: 100vh;
  max-width:auto;
}
.fade-enter-active {
  animation-name: fadeEnter;
  animation-duration: 1s;
  animation-iteration-count: 1;
}
.fade-move {
  transition: all 1s;
}
.fade-leave-active {
  animation-name: fadeLeave;
  animation-duration: 1s;
  animation-iteration-count: 1;
  position: absolute;
}
@keyframes fadeEnter {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@keyframes fadeLeave {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
</style>