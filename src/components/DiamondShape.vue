<script setup>
const props = defineProps({
  type: String,
  content: String,
});
</script>

<template>
  <div class="sized-div">
    <div class="shape">
      <div :class="type"></div>
    </div>
  </div>
</template>

<style scoped lang="sass">
  @import '../assets/sass/variables'

.sized-div
  position: relative
  outline: 1px solid orange
  aspect-ratio: 1/1

  .shape
    position: absolute
    top: 50%
    left: 50%
    transform: translate(-50%, -50%) rotate(45deg)
    height: 70.71%
    width: 70.71%
    border-radius: 0.5rem
    overflow: hidden

    .image
      position: absolute
      top: 50%
      left: 50%
      transform: translate(-50%, -50%) rotate(-45deg) scale(1.4)
      width: 100%
      aspect-ratio: 1/1
      background-position: center
      background-repeat: no-repeat
      background-size: cover

    .icon
      content: ''
</style>
