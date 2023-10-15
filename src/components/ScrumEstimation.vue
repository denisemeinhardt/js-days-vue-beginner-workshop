<template>
  <div class="container">
    <h1 class="funnyHeadline">Planning poker</h1>
    <div :title="anotherFunnyText">
      <ScrumEstimationCard
        v-for="value in selectedPoker"
        :key="value"
        :card-value="value"
        :selected-card-value="selectedCard"
        @my-event="selectCard"
      />
    </div>
    <button @click="resetCards()">Reset cards</button>
    <select v-model="selectedPoker">
      <option :value="scrumEstimationValues.fibonacci">Fibonacci</option>
      <option :value="scrumEstimationValues.shirtSize">Tshirt sizes</option>
    </select>
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue";
import ScrumEstimationCard from "./ScrumEstimationCard.vue";
import scrumEstimationValues from "@/services/scrumEstimationValuesProvider";
const anotherFunnyText = ref<string>("hello again");
const selectedCard = ref<string>();
const selectCard = (card: string) => {
  selectedCard.value = card;
};
const resetCards = () => {
  selectedCard.value = undefined;
};
const selectedPoker = ref(scrumEstimationValues.fibonacci);
</script>

<style lang="scss" scoped>
@import "../style/_scrumestimation_card.scss";
.funnyHeadline {
  color: red;
  font-size: 20px;
}
.container {
  text-align: center;
}
</style>
