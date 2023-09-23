<template>
  <div class="container">
    <h1 class="headline">Awesome scrum estimation</h1>
    <div
      v-for="estimationValue in estimationValuesToShow"
      :key="estimationValue"
      class="awesomescrumestimation-card"
      :class="
        selectedValue === estimationValue
          ? 'awesomescrumestimation-card--selected'
          : ''
      "
      @click="selectCard(estimationValue)"
    >
      {{ estimationValue }}
    </div>
    <div>
      <button @click="removeSelection">Remove selection</button>
    </div>
    <div>
      <select v-model="selectedSelectionType">
        <option
          v-for="type in possibleSelectionTypes"
          :key="type"
          :value="type"
        >
          {{ type }}
        </option>
      </select>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref, computed } from "vue";
import scrumEstimationValues from "@/services/scrumEstimationValuesProvider";

const selectedValue = ref<string | undefined>(undefined);
const possibleSelectionTypes = ref(Object.keys(scrumEstimationValues));
const selectedSelectionType =
  ref<keyof typeof scrumEstimationValues>("fibonacci");
const estimationValuesToShow = computed(
  () => scrumEstimationValues[selectedSelectionType.value]
);

const selectCard = (valueToSelect: string) => {
  selectedValue.value = valueToSelect;
};
const removeSelection = () => {
  selectedValue.value = undefined;
};
</script>

<style scoped lang="scss">
@import "src/style/scrumestimation_card";
.headline {
  color: red;
  font-size: 20px;
}

.container {
  text-align: center;
}
</style>
