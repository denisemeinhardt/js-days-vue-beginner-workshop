<template>
  <div class="container">
    <h1 class="headline">Headline</h1>
    <div>{{ divText }}</div>
  </div>
</template>

<script lang="ts" setup>
const divText = "someText";
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
