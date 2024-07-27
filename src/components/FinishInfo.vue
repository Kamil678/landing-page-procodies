<template>
  <div class="finish-info-item">
    <p class="finish-info-title">{{ finishInfoTitle }}</p>
    <p class="finish-info-text">{{ finishInfoText }}</p>
  </div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

defineProps({
  finishInfoTitle: String,
  finishInfoText: String,
});
</script>

<style lang="scss">
.finish-info-item {
  p {
    line-height: 16px;

    &.finish-info-title {
      font-size: 12px;
      font-weight: 600;
      margin-bottom: 4px;
    }

    &.finish-info-text {
      font-size: 10px;
      font-weight: 400;
    }
  }
}
</style>
