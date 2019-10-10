<template>
  <div class="task3">

    <!-- <div>
      Show limit:
      <input
        class="limit"
        type="number"
        min="0"
        :max="limitedItems.length"
        v-model.number="showLimit"
      />
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Items limit:
      <input
        class="limit"
        type="number"
        min="0"
        :max="items.length"
        v-model.number="itemsLimit"
      />
    </div> -->

    <Carousel :items="items.slice(0, this.itemsLimit)" :limit="showLimit" />
  </div>
</template>

<script>
import Carousel from "@/components/Carousel.vue";

export default {
  name: "Task3",
  components: {
    Carousel
  },
  data() {
    return {
      showLimit: 3,
      items: [
        { id: 0, path: require("../assets/notus-task3-img1.jpg")},
        { id: 1, path: require("../assets/notus-task3-img2.jpg")  },
        { id: 2, path: require("../assets/notus-task3-img3.jpg")  },
        { id: 3, path: require("../assets/notus-task3-img4.jpg")  },
      ],
    itemsLimit: 4,
    };
  },
  computed: {
    limitedItems() {
      return this.items.slice(0, this.itemsLimit);
    }
  },
  watch: {
    itemsLimit(newItemsLimit) {
      if (this.showLimit > newItemsLimit) this.showLimit = newItemsLimit;
      else if (newItemsLimit > 0 && this.showLimit === 0)
        this.showLimit = newItemsLimit;
    }
  }
};
</script>

<style>

.limit {
  margin: 0 auto;
  width: 20px;
}
.task3{
    margin-top:10%;
    height:100vh;
}
</style>
