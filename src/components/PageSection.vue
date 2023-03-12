<script setup>
const props = defineProps({
  sectionHeight: String,
});
</script>

<template>
  <section>
    <slot></slot>
  </section>
</template>

<style scoped lang="sass">
  @import "../assets/sass/variables"

section
  min-height: v-bind("props.sectionHeight")
  padding: $base-spacing
</style>
