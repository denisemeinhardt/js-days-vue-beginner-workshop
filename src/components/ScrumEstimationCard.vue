<template>
  <div
    @click="setSelectedCard(props.cardValue)"
    class="awesomescrumestimation-card"
    :class="{
      'awesomescrumestimation-card--selected': isSelected(props.cardValue),
    }"
  >
    {{ props.cardValue }}
  </div>
</template>

<script lang="ts" setup>
const props = defineProps<{
  cardValue: string;
  selectedCardValue?: string;
}>();
const emit = defineEmits<{ (e: "my-event", value: string): void }>();
const setSelectedCard = (value: string) => {
  emit("my-event", value);
};
const isSelected = (value: string) => {
  if (value === props.selectedCardValue) {
    return true;
  }
  return false;
};
</script>

<style lang="scss" scoped>
@import "../style/_scrumestimation_card.scss";
</style>
