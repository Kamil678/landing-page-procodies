<template>
  <header>
    <CarouselImage />
    <div class="header-content">
      <h1>Chance to win a StockX Mystery Box today!</h1>
      <p>Unleash the Excitement of Mystery Electronics</p>
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
  width: 100%;
  flex-direction: column;
  justify-content: center;
  gap: 20px 21px;
  align-items: center;
  color: #293632;

  @media (min-width: 992px) {
    flex-direction: row;
  }

  .header-content {
    h1 {
      font-size: 40px;
      line-height: 42px;
      font-weight: 800;
      text-align: center;

      @media (min-width: 992px) {
        font-size: 52px;
        line-height: 55px;
        text-align: left;
      }
    }

    p {
      font-size: 18px;
      line-height: 20px;
      font-weight: 400;
      text-align: center;
      margin: 8px 0 23px 0;

      @media (min-width: 992px) {
        font-size: 22px;
        line-height: 25.78px;
        text-align: left;
      }
    }
  }
}
</style>
