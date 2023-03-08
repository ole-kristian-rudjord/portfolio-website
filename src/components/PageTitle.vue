<script setup>
defineProps({
  color: String,
  mainText: String,
  smallText: String,
});
</script>

<template>
  <h1>
    <div id="div1"></div>
    <div id="div2"></div>
    <span v-if="smallText !== undefined">{{ smallText }}</span
    >{{ mainText }}
  </h1>
</template>

<style scoped lang="sass">
h1
  position: relative
  width: min-content
  padding-left: 4rem
  margin-left: -4rem
  margin-bottom: 4rem
  font-size: 3rem
  white-space: nowrap
  color: rgb(215, 215, 215)

  div
    position: absolute
    top: 50%
    left: 0
    transform: translateY(-50%)
    height: calc( 100% + 2rem )
    width: 1rem
    border-radius: 0.25rem
    background-color: rgb(215, 215, 215)

    &#div1
      box-shadow: 0 0 0 3px rgb(25, 25, 25)

    &#div2
      margin: 6px 8px
      background-color: v-bind(color)
      z-index: -1

  span
    font-size: 2rem
    display: block
</style>
