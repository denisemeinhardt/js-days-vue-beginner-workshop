<template>
  <div class="container">
    <h1 class="funnyHeadline">Planning poker</h1>
    <div :title="anotherFunnyText">
      <li
        v-for="value in selectedPoker"
        :key="value"
        @click="setSelectedCard(value)"
        class="awesomescrumestimation-card"
        :class="{ 'awesomescrumestimation-card--selected': isSelected(value) }"
      >
        {{ value }}
      </li>
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
import scrumEstimationValues from "@/services/scrumEstimationValuesProvider";
const anotherFunnyText = ref<string>("hello again");
const resetCards = () => {
  selectedCard.value = undefined;
};
const selectedCard = ref<string>();
const setSelectedCard = (value: string) => {
  selectedCard.value = value;
};
const isSelected = (value: string) => {
  if (value === selectedCard.value) {
    return true;
  }
  return false;
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
