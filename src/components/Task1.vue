<template>
  <div id="slider">
    <Slider1 :image="images[chosenImage]" />
    <img class="notus-logo" src="../assets/Notus-logo-main.svg" alt="">
    <div class="previous" @click="previous()"><img class="img-prev" src="../assets/next.svg" alt=""></div>
    <div class="counter"><p>{{this.counter}}/{{this.images.length}}</p></div>
    <div class="next" @click="next()"><img class="img-next" src="../assets/next.svg" alt=""></div>
    <h1 class="notus-text">Notus Front-end test</h1>
  </div>
</template>
    
<script>
import Slider1 from "@/components/Slider1.vue";

export default {
  name: "Task1",
  components: {
    Slider1
  },
  data() {
    return {
      images: [
        {
          id: 0,
          path: require("../assets/notus-task1-img1.jpg")
        },
        {
          id: 1,
          path: require("../assets/notus-task1-img2.jpg")
        },
        {
          id: 2,
          path: require("../assets/notus-task1-img3.jpg")
        }
      ],
      chosenImage: 0,
      counter:1
    };
  },
  methods: {
    previous() {
      this.moveLeft();
    },
    next() {
      this.moveRight();
    },
    moveLeft() {
      let flag = this.chosenImage;
      flag--;
      this.counter--;
      if (flag < 0) {
        flag = this.images.length - 1;
        this.counter-1;
      }
      this.chosenImage = flag;
    },
    moveRight() {
      let flag = this.chosenImage;
      flag++;
      this.counter++;
      if (flag >= this.images.length) {
        flag = 0;
        this.counter = 1;
      }
      this.chosenImage = flag;
    }
  }
};
</script>

<style>
#slider {
  position: relative;
  overflow: hidden;
}

#slider .next,
#slider .previous {
position:absolute;
z-index:2;
bottom:10%;
}
#slider .previous {
left:0;
right:10%;
bottom:10%;
}
#slider .next{
left:10%;
right:0;
}
.img-prev{
    transform: rotate(180deg);
}
.notus-logo {
  position: absolute;
  z-index: 2;
  left: 50%;
  margin-left: -50px;
  top:0;
  margin-top:40px;
}
.notus-text{
    position: absolute;
    z-index:2;
    color:#fff;
    font-weight: bold;
    font-size:60px;
    bottom: 40%;
    text-align: center;
    left: 0;
    right:0;
}
.counter{
    position:absolute;
    z-index:2;
    color:#fff;
    font-weight: 100;
    bottom:8.8%;
    left:0;
    right:0;
    font-size:19px;
    opacity:0.6;
}
</style>
