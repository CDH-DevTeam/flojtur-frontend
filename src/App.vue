<template>
  <div id="app">
    <router-view :key="$route.path" />
    <Footer />
  </div>
</template>

<script>
import Footer from "@/components/Footer.vue";

export default {
  components: { Footer },
};
</script>

<style lang="scss">
body {
  font-family: "Yanone Kaffeesatz", "PT Sans Narrow", "Arial Narrow", sans-serif;
  font-weight: 100;
  color: black;
  margin: 0;
  padding: 0;
  font-size: 20px;
  -webkit-text-size-adjust: 100%;
  background: rgb(215, 215, 210);
}

a:link,
a:hover,
a:active {
  text-decoration: none;
  color: inherit;
}

a:visited {
  text-decoration: underline;
  color: inherit;
  text-decoration-style: wavy;
}

h1 {
  font-weight: 100;
  font-style: normal;
  font-size: 60px;
  line-height: 1;
  margin: 60px 0 20px;

  &#site-title {
  }
}

h2 {
  font-weight: 100;
  font-size: 35px;
  line-height: 1;
  margin: 40px 0 0;
}

#ItemBack {
  cursor: pointer;
  position: absolute;
  left: 30px;
  height: 50px;
  width: 50px;
  border-radius: 50%;
  background: url(/interface/back-black.png);
  background-size: 35px 35px;
  background-repeat: no-repeat;
  background-position: center;
  z-index: 2000;
  margin-top: -5px;
  padding: 5px;

  @media screen and (max-width: 950px) {
    left: 20px;
    height: 40px;
    width: 40px;
    background-size: 30px 30px;
  }
  @media screen and (max-width: 800px) {
    position: static;
    margin: 0;
    padding: 0;

    + h1 {
      margin-top: 25px;
    }
  }
}

#ItemBack:hover {
  background-color: rgb(245, 245, 245);
}

.container {
  width: 80%;
  margin: auto;
}

.articleContainer {
  width: 65%;
  margin-top: 50px;
  margin-left: auto;
  margin-right: auto;
  border-radius: 10px;
  hyphens: auto;
  h2 {
    margin-bottom: 0.5em;
  }
}

@media screen and (max-width: 800px) {
  .container,
  .articleContainer {
    width: 90%;
  }
}

.articleIngress {
  font-size: 24px;
  margin-right: auto;
  column-count: 2;
  column-gap: 40px;
  line-height: 1.3;
  font-weight: 100;

  @media screen and (max-width: 1100px) {
    column-count: 1;
    font-size: 24px;
  }
}

.articletext {
  margin-top: 30px;
  text-align: justify;
  column-count: 3;
  column-gap: 40px;
  line-height: 1.3;
  font-weight: 300;

  @media screen and (max-width: 1100px) {
    column-count: 2;
    orphans: 2;
  }

  @media screen and (max-width: 800px) {
    column-count: 1;
    font-size: 22px;
  }

  a:link {
    text-decoration: none;
    color: black;
  }
}

.articletext:not(.footnotes) p,
.articleIngress p {
  margin: 0;

  & + p {
    text-indent: 1em;
  }
}

.articlepage {
  margin-bottom: 5em;
  .articleIngress {
    columns: 1;
  }
  .articletext {
    columns: 17em;
  }
}

.outset-small {
  margin-left: -6px;
  margin-right: -6px;
}

.outset-large {
  margin-left: -12px;
  margin-right: -12px;
}

.ActivateBonusMaterialText {
  display: inline-block;
  margin-left: -10px;
  font-size: 22px;
  line-height: 1;
  color: black;
  margin-right: auto;
  height: auto;
  padding: 10px 10px 8px 10px;
  border-radius: 10px;
  margin-top: 20px;
  cursor: pointer;
}

.ActivateBonusMaterialText:hover {
  background-color: rgb(245, 245, 245);
  color: black;
}

.dark-plate {
  box-shadow: 0px 10px 30px 0px rgba(0, 0, 0, 0.2),
    0 6px 40px 0 rgba(0, 0, 0, 0.19);
  padding: 30px;
  border-radius: 20px;
  color: white;
  background-color: RGBA(50, 50, 50, 1);
}

ul {
  padding-left: 1em;
  li {
    text-indent: 0;
  }
}

.footnotes > * {
  break-inside: avoid;
}
.footnotes p {
  margin: 0;
  padding-bottom: 0.5em;
}

.span-columns {
  column-span: all;
}

.long-url {
  word-break: break-all;
}

@media screen and (max-width: 800px) {
  body .sm-hidden {
    display: none;
  }
}

sup {
  line-height: 0;
}

img {
  max-width: 100%;
}

blockquote {
  margin: 1em;
}

hr {
  border: none;
  border-top: thin solid gray;
}

figure {
  text-align: center;
}

.clearfix::after {
  content: "";
  display: block;
  clear: both;
}
</style>
