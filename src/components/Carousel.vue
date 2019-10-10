<template>
  <div>
    <div class="carousel">
      <!-- <a class="carousel-nav" @click="prev">&#x3C; PREV</a> -->
      <div class="carousel-nav" @click="prev">
        <img class="img-prev" src="../assets/next.svg" alt />
      </div>
      <div class="carousel-items">
        <div class="carousel-item" v-for="item in itemsShown" :key="item.id">
          <img :src="item.path" alt />
        </div>
      </div>
      <!-- <a class="carousel-nav"  @click="next">NEXT &#x3E;</a> -->
      <div class="carousel-nav" @click="next">
        <img class="img-next" src="../assets/next.svg" alt />
      </div>
    </div>
    <!-- :style="{ background: `url(${item.path})` }" -->
    <!-- <p class="debug">CURRENT OFFSET: {{ offset }}</p> -->
  </div>
</template>

<script>
export default {
  name: "Carousel",
  props: {
    items: Array,
    limit: Number
  },
  data() {
    return {
      offset: 0
    };
  },
  computed: {
    maxOffset() {
      return this.items.length - 1;
    },
    itemsOrdered() {
      // Cut array into two parts and replace them
      const cutFromBegin = this.items.slice(0, this.offset);
      const cutFromEnd = this.items.slice(this.offset, this.items.length);

      return [...cutFromEnd, ...cutFromBegin];
    },
    itemsShown() {
      return this.itemsOrdered.slice(0, this.limit);
    }
  },
  methods: {
    prev() {
      if (this.offset <= 0) this.offset = this.maxOffset;
      else this.offset = this.offset - 1;
    },
    next() {
      if (this.offset >= this.maxOffset) this.offset = 0;
      else this.offset = this.offset + 1;
    }
  },
  watch: {
    items() {
      // Reset offset when items changed
      this.offset = 0;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.carousel {
  margin-top: 2rem;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #081b2f;
  top: 0;
  left: 0;
  right: 0;
  height: 100vh;
  opacity: 1;
}

/* .carousel-nav {
  color: #42b983;
  text-decoration: none;
  margin: 0 1rem;
} */

.carousel-items {
  display: flex;

  /* grid-template-columns: repeat(5, 1fr);
grid-template-rows: repeat(5, 1fr);
grid-column-gap: 0px;
grid-row-gap: 0px;  */
}

.carousel-item {
  width: 500px;
  height: 560px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.img-prev {
  transform: rotate(180deg);
}
</style>
