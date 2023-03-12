<script setup></script>

<template>
  <div></div>
</template>

<style scoped lang="sass">
  @import "../assets/sass/variables"
div
  position: fixed
  top: 0
  left: 0
  height: 100vh
  width: 100vw
  background-color: transparent
  background-image: radial-gradient($primary-color 1.5px, transparent 0)
  background-size: 2rem 2rem
  background-position: 100% 100%
  background-attachment: fixed
  opacity: 0.2
  z-index: -999
</style>
