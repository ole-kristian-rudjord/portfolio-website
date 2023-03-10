<script setup>
defineProps({
  mainText: String,
});
</script>

<template>
  <p>{{ mainText }}</p>
</template>

<style scoped lang="sass">
p
  color: rgb(215, 215, 215)
  line-height: 1.5
  font-weight: 400
  margin-bottom: 1rem
</style>
