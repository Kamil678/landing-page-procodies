<template>
  <footer>
    <p class="accept-credit-cards-text">We accept the following credit cards</p>
    <div class="credit-cards-container">
      <img src="../assets//accept-credit-cards.png" alt="Accept credit cards" />
    </div>
  </footer>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

defineProps({
  finishInfoTitle: String,
  finishInfoText: String,
});
</script>

<style lang="scss">
footer {
  margin: 16px 0;

  @media (min-width: 992px) {
    margin: 16px 18px;
    width: 100%;
  }

  img {
    width: 250px;

    @media (min-width: 992px) {
      width: auto;
      height: 40px;
    }
  }

  .accept-credit-cards-text {
    margin-bottom: 4px;
    text-align: center;
    font-size: 12px;
    font-weight: 400;
    line-height: 16px;
  }

  .credit-cards-container {
    height: auto;
    text-align: center;

    @media (min-width: 992px) {
      height: 40px;
    }
  }
}
</style>
