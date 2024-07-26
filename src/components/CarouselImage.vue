<template>
  <div class="carousel-container">
    <div class="main-image">
      <img
        :src="activeImage.src"
        :alt="activeImage.alt"
        width="481"
        height="480"
        :data-id="activeImage.id"
      />
    </div>
    <div class="other-images">
      <button
        v-for="image in images.filter((image) => image.id !== activeImage.id)"
        @click="onChangeImage"
      >
        <img
          :src="image.src"
          :alt="image.alt"
          width="132"
          height="132"
          :data-id="image.id"
        />
      </button>
    </div>
    <div class="value-container">
      <p class="current-value">$1.99</p>
      <p class="original-value">Original value $500</p>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const images = [
  {
    id: 1,
    src: new URL("../assets/image1.png", import.meta.url).href,
    alt: "Image 1",
  },
  {
    id: 2,
    src: new URL("../assets/image2.png", import.meta.url).href,
    alt: "Image 2",
  },
  {
    id: 3,
    src: new URL("../assets/image3.png", import.meta.url).href,
    alt: "Image 3",
  },
  {
    id: 4,
    src: new URL("../assets/image4.png", import.meta.url).href,
    alt: "Image 4",
  },
];

const activeImage = ref(images[0]);

const onChangeImage = (e) => {
  activeImage.value = images[e.target.getAttribute("data-id") - 1];
};
</script>

<style lang="scss">
.carousel-container {
  position: relative;

  .other-images {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;

    button {
      background-color: transparent;
      border: none;
      cursor: pointer;
    }
  }

  .value-container {
    width: 160px;
    height: 160px;
    position: absolute;
    top: 0;
    right: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 8px 0;
    padding: 46px 20px 45px 20px;
    border-radius: 50%;
    background-color: #006340;
    color: #fff;

    .current-value {
      font-size: 38px;
      font-weight: 700;
      line-height: 44.53px;
      text-align: center;
    }

    .original-value {
      font-size: 14px;
      font-weight: 400;
      line-height: 16.41px;
      text-align: center;
    }
  }
}
</style>
