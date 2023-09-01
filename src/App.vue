<script setup lang="ts">
import Demo  from './Demo.vue'
</script>
<template>
  <div class="container">
    <Demo />
  </div>
</template>

<style>
body {
  margin: 0;
}
.container {
  display: flex;
  flex-direction: column;
  height: 500px;
  overflow: hidden;
  background: pink;
}
</style>