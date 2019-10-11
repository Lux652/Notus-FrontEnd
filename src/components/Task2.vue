<template>
  <div class="parent" id="task3">
    <div class="div1">
      <p class="task2-text">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duo Reges:
        constructio interrete. Ut aliquid scire se gaudeant? Illi enim inter se
        dissentiunt. Nec vero sum nescius esse utilitatem in historia, non modo
        voluptatem. Quamquam te quidem video minime esse deterritum.
      </p>
    </div>
    <div class="div2">
      <img src="../assets/notus-task2-img1.jpg" alt />
    </div>
    <div class="div3">
      <img src="../assets/notus-task2-img3.jpg" alt />
    </div>
    <div class="div4">
      <img src="../assets/notus-task2-img2.jpg" alt />
    </div>
    <div class="div5">
      <img src="../assets/notus-task2-img4.jpg" alt />
    </div>
  </div>
</template>

<script>
export default {
  name: "Task2"
};
</script>

<style scoped>
@media (min-width: 1281px) {
  .parent {
    display: grid;
    grid-template-columns: repeat(3, 1fr) 1fr repeat(3, 1fr);
    grid-template-rows: repeat(3, 1fr);
    grid-column-gap: 1.5%;
    grid-row-gap: 1%;
    align-items: center;
    justify-content: center;
  }

  .div1 {
    grid-area: 1 / 3 / 2 / 6;
  }
  .div2 {
    grid-area: 2 / 4 / 3 / 5;
  }
  .div3 {
    grid-area: 3 / 4 / 4 / 5;
  }
  .div4 {
    grid-area: 2 / 5 / 4 / 6;
  }
  .div5 {
    grid-area: 2 / 3 / 4 / 4;
  }
}

@media (min-width: 1025px) and (max-width: 1280px) {
  .parent {
    display: grid;
    grid-template-columns: repeat(auto-fill);
  }
}

@media (min-width: 768px) and (max-width: 1024px) {
  img {
    max-width: 80%;
  }
}

@media (min-width: 481px) and (max-width: 767px) {
  img {
    max-width: 80%;
  }
}

@media (max-width: 480px) {
  img {
    max-width: 80%;
  }
}
</style>
