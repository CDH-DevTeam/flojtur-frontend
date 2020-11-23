<template>
  <div>
    <div id="ItemTopImage">
      <div
        id="openseadragon1"
        style="position: relative; width: 100%; height: 70vh"
      ></div>
    </div>

    <main id="main">
      <router-link
        :to="{ name: 'InstrumentPage', params: { id: this.automId } }"
      >
        <div id="ItemBack"></div>
      </router-link>

      <h2 style="margin-top: 70px">Bildens titel om s&aring;dan finnes</h2>

      <a href="/images/hopehist1.jpg">
        <div class="DownloadContainer">
          <div class="DownloadButton"></div>
          <div class="DownloadLabel">Ladda ner</div>
        </div>
      </a>

      <div id="gallery" style="margin-top: 40px">
        <MiniGallery
          masonryId="masonry-speluret"
          full="1"
          :items="
            photos.map((hit) => ({
              link: {
                name: 'ImagePage',
                params: {
                  automId,
                  category: category,
                  imageId: hit.id,
                },
              },
              image: `https://data.dh.gu.se/flojtur/300x/${hit.thumbnail}`,
            }))
          "
        />
      </div>
    </main>

    <div id="foot" style="float: left; width: 100%"></div>
  </div>
</template>

<script>
import OpenSeadragon from "openseadragon";
import { search } from "@/assets/db";
import MiniGallery from "@/components/MiniGallery";

export default {
  name: "ImagePage",
  props: ["automId", "category", "imageId"],
  components: { MiniGallery },
  data() {
    return {
      photos: [],
    };
  },
  created() {
    search(`photo${this.category}`, "").then(({ features }) => {
      this.photos = features;
    });
  },
  mounted() {
    OpenSeadragon({
      id: "openseadragon1",
      homeFillsViewer: false,
      minZoomImageRatio: 0.3,

      showZoomControl: false,
      showHomeControl: false,

      prefixUrl: "/openseadragon/",
      tileSources: "/graphics/hopehist1.dzi",
    });
  },
};
</script>

<style scoped>
#ItemBack {
  margin-top: -10px;
}

.DownloadContainer {
  width: auto;
  margin-top: 40px;
  margin-left: -10px;
  border-radius: 10px;
  padding: 10px;
}

.DownloadContainer:hover {
  background-color: rgb(245, 245, 245);
}

.DownloadButton {
  cursor: pointer;
  border-radius: 5px;
  border-style: solid;
  border-width: 1px;
  border-color: #666666;
  background: url(/interface/download.png);
  background-size: 20px 20px;
  background-repeat: no-repeat;
  background-position: center;
  float: left;
  font-size: 12px;
  width: 30px;
  height: 30px;
  position: relative;
  margin-right: 20px;
}

.DownloadLabel {
  margin-top: 5px;
  cursor: pointer;
  color: black;
  font-weight: 300;
  font-size: 25px;
  position: relative;
}

@media screen and (max-width: 800px) {
  .DownloadLabel {
    margin-top: -4px;
    font-size: 32px;
  }
}
</style>