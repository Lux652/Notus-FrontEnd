<template>
  <div id="slider">
    <Slider1 :image="images[chosenImage]" />
    <div class="btn-menu">
      <p>Menu</p>
      <button @click="toggleMenu">
        <img src="../assets/notus-meni.svg" alt />
      </button>
    </div>
    <Menu :model="showMenu" @toggle-menu="toggleMenu" />
    <img class="notus-logo" src="../assets/Notus-logo-main.svg" alt />

    <button class="previous" @click="previous()">
      <img class="img-prev" src="../assets/next.svg" alt />
    </button>

    <div class="counter">
      <p>{{ this.counter }}/{{ this.images.length }}</p>
    </div>
    <button class="next" @click="next()">
      <img class="img-next" src="../assets/next.svg" alt />
    </button>

    <h1 class="notus-text">Notus Front-end test</h1>
  </div>
</template>

<script>
import Slider1 from "@/components/Slider1.vue";
import Menu from "@/components/Menu.vue";

export default {
  name: "Task1",
  components: {
    Slider1,
    Menu
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
      counter: 1,
      showMenu: false
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
      //   this.counter--;
      if (flag < 0) {
        flag = this.images.length - 1;
      }
      this.chosenImage = flag;
      this.counter = this.chosenImage + 1;
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
    },
    toggleMenu() {
      this.showMenu = !this.showMenu;
    }
  }
};
</script>

<style>
/* #slider {
  position: relative;
  overflow: hidden;
} */

.notus-text {
  position: absolute;
  z-index: 2;
  color: #fff;
  font-weight: bold;
  bottom: 40%;
  text-align: center;
  left: 0;
  right: 0;
}
#slider .previous {
  position: absolute;
  z-index: 3;
  bottom: 10%;
  left: 45%;
  margin-bottom: 10px;
}
#slider .next {
  position: absolute;
  z-index: 2;
  bottom: 10%;
  right: 45%;
  margin-bottom: 10px;
}
button {
  background: none;
  border: none;
}

.img-prev {
  transform: rotate(180deg);
}
.notus-logo {
  position: absolute;
  z-index: 2;
  left: 50%;
  margin-left: -50px;
  top: 0;
  margin-top: 40px;
}
.btn-menu {
  position: absolute;
  z-index: 2;
  left: 5%;
  top: 0;
  margin-top: 40px;
}
.btn-menu p {
  color: #ffffff;
  margin-bottom: -2%;
  font-size: 12px;
}
.btn-menu button {
  background: none;
  border: none;
}

.counter {
  position: absolute;
  z-index: 2;
  color: #fff;
  font-weight: 100;
  bottom: 9.5%;
  left: 0;
  right: 0;
  font-size: 19px;
  opacity: 0.6;
}

@media (min-width: 1281px) {
  .notus-text {
    font-size: 60px;
  }

  .notus-logo {
    position: absolute;
    z-index: 2;
    left: 50%;
    margin-left: -50px;
    top: 0;
    margin-top: 40px;
  }
}

@media (min-width: 1025px) and (max-width: 1280px) {
  .notus-text {
    font-size: 40px;
  }

  #slider .previous {
    left: 44%;
  }
  #slider .next {
    right: 44%;
  }
}

@media (min-width: 768px) and (max-width: 1024px) {
  .notus-text {
    font-size: 40px;
  }

  .notus-logo {
    width: 10%;
    margin-left: -25px;
  }

  #slider .previous {
    left: 43.5%;
  }
  #slider .next {
    right: 43.5%;
  }
}

@media (min-width: 481px) and (max-width: 767px) {
  .notus-text {
    font-size: 30px;
  }

  .notus-logo {
    width: 8%;
    margin-left: -15px;
  }

  #slider .previous {
    left: 40%;
  }
  #slider .next {
    right: 40%;
  }
}

@media (max-width: 480px) {
  .notus-logo {
    width: 9%;
    margin-left: -15px;
  }
  #slider .previous {
    left: 35%;
  }
  #slider .next {
    right: 35%;
  }
}
</style>
