<template>
  <main>
    <h2>Top Tech Mystery Box at Unbeatable Prices</h2>
    <p class="info">
      Fast shipping | Easy returns | Special discounts for students
    </p>
    <BoxWithImage
      :image-src="firstImageUrl"
      image-alt="First product photo"
      title="Curious about the <span>StockX</span> Mystery Box?"
      first-text="Experience the thrill of unboxing cutting-edge gadgets with Stockx Mystery Boxes. Each box is a treasure trove of high-quality electronics, handpicked to elevate your tech game."
      second-text="Expect the unexpected! Our boxes are packed with the latest gadgets, from smartphones to gaming consoles, ensuring you get the best tech surprises every time."
      class="first-section"
    />
    <BoxWithImage
      :image-src="secondImageUrl"
      image-alt="First product photo"
      title="Why is everyone buzzing about these boxes?"
      first-text="StockX Mystery Boxes are not just about products; they’re about the experience. Imagine the excitement of unveiling top-tier electronics at a fraction of the cost."
      second-text="Our boxes include a variety of premium tech items, making it a must-have for every tech enthusiast. Join the buzz and see why everyone is raving about the unbeatable value and surprise factor of Stockx Mystery Boxes!"
      image-right
    />
    <section class="finish-info-container">
      <FinishInfo
        v-for="info in allInfo"
        :key="info.id"
        :finish-info-title="info.title"
        :finish-info-text="info.text"
      />
    </section>
  </main>
</template>

<script setup lang="ts">
import BoxWithImage from "./BoxWithImage.vue";
import FinishInfo from "./FinishInfo.vue";

const firstImageUrl = new URL("../assets/box-with-image-1.png", import.meta.url)
  .href;
const secondImageUrl = new URL(
  "../assets/box-with-image-2.png",
  import.meta.url
).href;

const allInfo = [
  {
    id: 1,
    title: "How can I win?",
    text: "Thanks to your membership, you also participate in our contest to win the iPhone15. We sellect a winner among every 600 participants. The next winner will be selected on 06.10.2023, and will be notified directly by e-mail. If the reward is out of stock, the winner will receive a similar product of equal or greater value instead.",
  },
  {
    id: 2,
    title: "No hidden fees?",
    text: "We ensure that our members are provided with a detailed history of transactions so that they know exactly what they are paying for. Credit card information is only required to facilitate future purchases. There will be no charges on your credit card statement if you do not upgrade to PREMIUM membership and do not make a purchase.",
  },
  {
    id: 3,
    title: "Why do we need your billing information?",
    text: "By joining this service, you will receive a 5-day trial of our partner's program. If you continue with a subscription beyond the 5-day trial period, you will be charged an amount on your credit card which varies depending on the choice of the tariff. When your contribution is deducted from your credit card or other payment method, you will have access to these services which are reserved exclusively for members of our partner's website.",
  },
];
</script>

<style lang="scss">
main {
  h2 {
    font-size: 38px;
    font-weight: 700;
    line-height: 42px;
    text-align: center;
    margin: 48px 0 8px 0;

    @media (min-width: 992px) {
      font-size: 48px;
      line-height: 52px;
    }
  }

  .info {
    font-size: 20px;
    font-weight: 500;
    line-height: 23.44px;
    text-align: center;
    color: #006340;
  }

  .first-section {
    margin: 32px 0 48px 0;
  }

  .finish-info-container {
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: space-between;
    gap: 16px 32px;
    background-color: #f5f5f5;
    padding: 24px 16px;
    margin-top: 48px;
    text-align: center;

    @media (min-width: 768px) {
      flex-direction: row;
      text-align: left;
    }
  }
}
</style>
