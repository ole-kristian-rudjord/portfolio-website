<script setup>
const props = defineProps({
  backgroundImageURL: String,
  size: String,
});
</script>

<template>
  <div class="sized-div" :style="{ height: `${props.size}` }">
    <div class="shape">
      <div
        class="content"
        :style="{
          backgroundImage: `url(${props.backgroundImageURL})`,
          height: `${props.size}`,
        }"
      ></div>
    </div>
  </div>
</template>

<style scoped lang="sass">
  @import '../assets/sass/variables'

.sized-div
  position: relative
  outline: 1px solid orange
  // height: 200px
  aspect-ratio: 1/1

  .shape
    position: absolute
    top: 50%
    left: 50%
    transform: translate(-50%, -50%) rotate(45deg)
    height: 70.71%
    width: 70.71%
    border: 2px solid $text-color
    border-radius: 0.5rem
    overflow: hidden

    .content
      position: absolute
      top: 50%
      left: 50%
      transform: translate(-50%, -50%) rotate(-45deg)
      aspect-ratio: 1/1
      background-position: center
      background-repeat: no-repeat
      background-size: cover
</style>
