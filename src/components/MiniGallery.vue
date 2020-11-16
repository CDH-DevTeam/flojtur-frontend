<template>
  <div
    v-masonry="masonryId"
    item-selector=".grid-item"
    :percent-position="true"
    :gutter="15"
    transition-duration="0s"
    class="grid"
    :class="{ collapsed }"
  >
    <router-link
      v-for="item in items"
      :key="item.link"
      tag="div"
      :to="item.link"
      class="grid-item"
    >
      <img :src="item.image" />
    </router-link>
  </div>
</template>

<script>
import imagesLoaded from "imagesloaded";

export default {
  name: "MiniGallery",
  props: ["masonryId", "items", "collapsed"],
  mounted() {
    imagesLoaded(`#${this.masonryId}`, () =>
      setTimeout(() => this.$redrawVueMasonry(this.masonryId), 100)
    );
  },
  watch: {
    collapsed() {
      setTimeout(() => this.$redrawVueMasonry(this.masonryId));
    },
  },
};
</script>

<style scoped>
.grid-item {
  width: 13.1%;
  transition: all 0.2s ease-in-out;
  background-color: black;
  margin-top: 0px;
}

@media screen and (max-width: 1500px) {
  .grid-item {
    width: 18.5%;
  }
  .grid.collapsed
    .grid-item
    + .grid-item
    + .grid-item
    + .grid-item
    + .grid-item
    + .grid-item {
    display: none;
  }
}

@media screen and (max-width: 1200px) {
  .grid-item {
    width: 23.5%;
  }
  .grid.collapsed
    .grid-item
    + .grid-item
    + .grid-item
    + .grid-item
    + .grid-item {
    display: none;
  }
}

@media screen and (max-width: 900px) {
  .grid-item {
    width: 31%;
  }
  .grid.collapsed .grid-item + .grid-item + .grid-item + .grid-item {
    display: none;
  }
}

@media screen and (max-width: 610px) {
  .grid-item {
    width: 48%;
  }
  .grid.collapsed .grid-item + .grid-item + .grid-item {
    display: none;
  }
}

.grid-item {
  float: left;
  transition: all 0.2s ease-in-out;
  overflow: hidden;
  margin-bottom: 15px;
}

.grid-item img {
  display: block;
  width: 100%;
  object-fit: cover;
  transition: all 0.2s ease-in-out;
}

.grid-item:hover {
  display: block;
  transform: scale(1.01);
  filter: brightness(120%);
}
</style>