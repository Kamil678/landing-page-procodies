<template>
  <section
    class="box-with-image-container"
    :class="imageRight ? 'image-right' : ''"
  >
    <div class="image-container">
      <img :src="imageSrc" :alt="imageAlt" width="583" height="583" />
    </div>
    <div class="text-container">
      <h3 v-html="title"></h3>
      <p class="first-text">{{ firstText }}</p>
      <p class="second-text">{{ secondText }}</p>
    </div>
  </section>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

defineProps({
  imageSrc: String,
  imageAlt: String,
  title: String,
  firstText: String,
  secondText: String,
  imageRight: Boolean,
});
</script>

<style lang="scss">
section.box-with-image-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0 32px;

  @media (min-width: 992px) {
    flex-direction: row;
  }

  &.image-right {
    @media (min-width: 992px) {
      flex-direction: row-reverse;
    }
  }

  .image-container {
    height: 300px;

    @media (min-width: 768px) {
      height: 583px;
    }

    img {
      border-radius: 30px;
      width: 300px;
      height: 300px;

      @media (min-width: 768px) {
        width: 583px;
        height: 583px;
      }
    }
  }

  .text-container {
    h3 {
      font-size: 32px;
      font-weight: 700;
      line-height: 42px;
      text-align: center;
      margin-top: 10px;

      @media (min-width: 992px) {
        text-align: left;
        margin-top: 0;
        font-size: 42px;
        font-weight: 700;
        line-height: 52px;
      }

      span {
        color: #2d473e;
      }
    }

    .first-text,
    .second-text {
      font-size: 16px;
      font-weight: 400;
      line-height: 24px;
      text-align: center;

      @media (min-width: 992px) {
        text-align: left;
      }
    }

    .first-text {
      margin: 24px 0 8px 0;
    }
  }
}
</style>
