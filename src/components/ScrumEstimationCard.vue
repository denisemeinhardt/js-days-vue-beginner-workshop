<template>
  <div
    class="awesomescrumestimation-card"
    :class="
      props.selectedValue === props.value
        ? 'awesomescrumestimation-card--selected'
        : ''
    "
    @click="emitSelected"
  >
    {{ props.value }}
  </div>
</template>

<script lang="ts" setup>
const props = defineProps<{
  value: string;
  selectedValue?: string;
}>();

const emit = defineEmits<{
  (event: "selected", value: string): void;
}>();

const emitSelected = () => {
  emit("selected", props.value);
};
</script>

<style lang="scss" scoped>
@import "src/style/scrumestimation_card";
</style>
