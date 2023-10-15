<template>
  <ToggleableCard
    :selected="isSelected(props.cardValue)"
    @click="setSelectedCard(props.cardValue)"
  >
    {{ props.cardValue }}
  </ToggleableCard>
</template>

<script lang="ts" setup>
import ToggleableCard from "./ToggleableCard.vue";

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
