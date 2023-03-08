<script setup>
defineProps({
  color: String,
});
</script>

<template>
  <section>
    <slot></slot>
  </section>
</template>

<style scoped lang="sass">
section
  min-height: 100dvh
  // outline: 2px solid rgb(100, 0, 0)
  padding: 4rem
</style>
