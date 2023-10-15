<template>
  <div class="container">
    <h1 class="funnyHeadline">This is fun</h1>
    <div class="funnyText" :title="anotherFunnyText">
      {{ funnyText }}
    </div>
    <button @click="resetText('lustiger')">Change funny text</button>
    <div>
      {{ anotherFunnyText + " - " + funnyText }}
    </div>
    <button @click="resetText('unlustiger')">
      Change funny text differently
    </button>
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue";
const funnyText = ref<string>("this even more");
const anotherFunnyText = ref<string>("hello again");
const resetText = (insertParameterHere: string) => {
  funnyText.value = insertParameterHere + " wirds nicht mehr";
};
</script>

<style lang="scss" scoped>
.funnyHeadline {
  color: red;
  font-size: 20px;
}
.container {
  text-align: center;
}
</style>
