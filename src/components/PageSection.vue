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
  width: 100%
  max-width: 1600px
  padding: $base-spacing
  margin: 0 auto
  margin-bottom: $base-spacing

  @media only screen and (max-width: 1024px)
    padding: calc($base-spacing / 4)
</style>
