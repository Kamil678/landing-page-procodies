<template>
  <header>
    <CarouselImage />
    <div>
      <h1>Chance to win a StockX Mystery Box today!</h1>
      <h4>Unleash the Excitement of Mystery Electronics</h4>
      <HeaderForm />
    </div>
  </header>
</template>

<script setup lang="ts">
import CarouselImage from "./CarouselImage.vue";
import HeaderForm from "./HeaderForm.vue";
</script>

<style lang="scss">
header {
  display: flex;
  align-items: center;
  gap: 0 16px;
  color: #293632;

  h1 {
    font-size: 52px;
    line-height: 55px;
    font-weight: 800;
  }

  h4 {
    font-size: 22px;
    line-height: 25.78px;
    font-weight: 400;
    margin: 8px 0 23px 0;
  }
}
</style>
