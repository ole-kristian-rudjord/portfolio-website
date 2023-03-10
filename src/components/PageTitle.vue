<script setup>
defineProps({
  color: String,
  mainText: String,
  smallText: String,
});
</script>

<template>
  <h1>
    <span v-if="smallText !== undefined" class="small-text">{{
      smallText
    }}</span>
    <span class="main-text"
      >{{ mainText }}
      <div></div
    ></span>
  </h1>
</template>

<style scoped lang="sass">
h1
  position: relative
  width: min-content
  margin-bottom: 4rem
  white-space: nowrap
  color: rgb(215, 215, 215)

  span
    filter: drop-shadow(0 0 3px rgba(25, 25, 25, 0.5))

  .small-text
    font-size: 2rem
    display: block

  .main-text
    font-size: 3rem

  div
    position: absolute
    bottom: -0.5rem
    left: 50%
    transform: translateX(-50%)
    height: 2rem
    width: calc( 100% + 0.5rem)
    border-radius: 2px
    background-color: v-bind(color)
    opacity: 0.5
    z-index: -1
</style>
