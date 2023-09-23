<template>
  <div class="container">
    <h1 class="headline">Headline</h1>
    <div :title="bodyTitle">{{ bodyText }} (hover to see tooltip)</div>
    <div>Concatenated: {{ titleAndText }}</div>
    <button @click="changeText('some other text')">Click me</button>
    <button @click="changeText('even more text')">Click me also</button>
  </div>
</template>

<script lang="ts" setup>
import { ref, computed } from "vue";

const bodyText = ref("Some text");
const bodyTitle = ref("Body title");

const changeText = (value: string): void => {
  bodyText.value = value;
};

const titleAndText = computed(
  (): string => bodyText.value + " " + bodyTitle.value
);
</script>

<style scoped lang="scss">
.headline {
  color: red;
  font-size: 20px;
}

.container {
  text-align: center;
}
</style>
