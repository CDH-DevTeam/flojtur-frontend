<template>
  <div>
    <div class="container">
      <div class="ornament lyre"></div>
      <h1 id="site-title">
        <router-link to="/">Pehr Strands flöjtur</router-link>
      </h1>
      <div class="subtitle">1791–1824</div>
      <div class="author" @click="scrollToFooter"><i>Johan Norrback</i></div>
    </div>
  </div>
</template>

<script>
import VueScrollTo from "vue-scrollto";

export default {
  name: "Title",
  mounted() {
    if (this.$route.hash) {
      VueScrollTo.scrollTo(this.$route.hash);
    }
  },
  methods: {
    scrollToFooter() {
      VueScrollTo.scrollTo("#footer");
    },
  },
};
</script>

<style lang="scss" scoped>
#site-title {
  font-size: 70px;
  text-align: center;
  margin: 20px 0 10px;
  padding-top: 0px;
  line-height: 0.9;
}

.subtitle {
  line-height: 1.5;
  text-align: center;
  font-size: 40px;
  margin-top: -10px;
}

.author {
  line-height: 1.5;
  text-align: center;
  font-size: 39px;
  margin-top: 30px;
  margin-left: -10px;
  margin-bottom: 100px;
  cursor: pointer;
}

.ornament {
  margin: 0 auto;
  background-size: contain;
  background-position: center;
  background-repeat: no-repeat;

  &.lyre {
    background-image: url(../assets/topdetailwhite.png);
    height: 235px;
    max-height: 20vh;
    width: 205px;
    margin-top: 80px;
  }
  &.laural {
    background-image: url(../assets/lauraldetailwhite.png);
    height: 175px;
    width: 200px;
  }
}

@media screen and (min-width: 800px) {
  #site-title {
    font-size: 120px;
  }

  .subtitle {
    font-size: 60px;
  }
}
</style>
