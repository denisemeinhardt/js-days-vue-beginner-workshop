<template>
  <div class="container">
    <h1 class="funnyHeadline">This is fun</h1>
    <div class="funnyText">
      {{ funnyText }}
    </div>
  </div>
</template>

<script lang="ts" setup>
const funnyText = "this even more";
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
