<template>
  <div class="carousel-container">
    <figure class="main-image">
      <img
        :src="activeImage.src"
        :alt="activeImage.alt"
        :data-id="activeImage.id"
      />
    </figure>
    <div class="other-images">
      <button
        v-for="image in images.filter((image) => image.id !== activeImage.id)"
        :key="image.id"
        @click="onChangeImage"
        :aria-label="`Change image to ${image.alt}`"
      >
        <img :src="image.src" :alt="image.alt" :data-id="image.id" />
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

const onChangeImage = (e: Event) => {
  const target = e.target as HTMLElement;
  const id = target.getAttribute("data-id");
  if (id) {
    activeImage.value = images[parseInt(id) - 1];
  }
};
</script>

<style lang="scss">
.carousel-container {
  position: relative;

  .main-image {
    img {
      width: 301px;
      height: 300px;

      @media (min-width: 768px) {
        width: 481px;
        height: 480px;
      }
    }
  }

  .other-images {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;

    button {
      background-color: transparent;
      border: none;
      cursor: pointer;

      img {
        width: 100px;
        height: 100px;
        border: 0.93px solid #006340;
        border-radius: 15px;

        @media (min-width: 992px) {
          width: 132px;
          height: 132px;
        }
      }
    }
  }

  .value-container {
    width: 120px;
    height: 120px;
    position: absolute;
    top: -16px;
    right: -5px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 8px;
    padding: 46px 20px 45px 20px;
    border-radius: 50%;
    background-color: #006340;
    color: #fff;

    @media (min-width: 992px) {
      width: 160px;
      height: 160px;
    }

    .current-value {
      font-size: 28px;
      font-weight: 700;
      line-height: 34px;
      text-align: center;

      @media (min-width: 992px) {
        font-size: 38px;
        line-height: 44.53px;
      }
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
