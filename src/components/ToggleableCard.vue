<template>
  <div
    class="awesomescrumestimation-card"
    :class="{
      'awesomescrumestimation-card--selected': props.selected,
    }"
  >
    <slot />
  </div>
</template>

<script lang="ts" setup>
const props = withDefaults(
  defineProps<{
    selected?: boolean;
  }>(),
  { selected: false },
);
</script>

<style lang="scss" scoped>
@import "../style/_scrumestimation_card.scss";
</style>
