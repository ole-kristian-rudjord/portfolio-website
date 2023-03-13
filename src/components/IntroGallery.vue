<script setup>
import { onMounted } from 'vue';

onMounted(() => {
  const main = document.querySelector('#image-main');

  main.style.backgroundImage =
    document.querySelector('#image-0').style.backgroundImage;

  document.querySelectorAll('.gallery-image').forEach((image) => {
    image.addEventListener('mouseover', () => {
      const hoveredImage = document.getElementById(image.id);
      main.style.backgroundImage = hoveredImage.style.backgroundImage;
    });
  });
});

const images = [
  'https://images.unsplash.com/photo-1546776310-eef45dd6d63c?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=810&q=80',
  'https://images.unsplash.com/photo-1534723328310-e82dad3ee43f?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8NHx8cm9ib3R8ZW58MHx8MHx8&auto=format&fit=crop&w=500&q=60',
  'https://images.unsplash.com/photo-1589254065909-b7086229d08c?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8NXx8cm9ib3R8ZW58MHx8MHx8&auto=format&fit=crop&w=500&q=60',
  'https://images.unsplash.com/photo-1601132359864-c974e79890ac?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTF8fHJvYm90fGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=500&q=60',
  'https://images.unsplash.com/photo-1580835239846-5bb9ce03c8c3?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTV8fHJvYm90fGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=500&q=60',
  'https://images.unsplash.com/photo-1555255707-c07966088b7b?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTd8fHJvYm90fGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=500&q=60',
];
</script>

<template>
  <div id="main-content">
    <div
      v-for="(image, index) in images"
      :id="'image-' + index"
      class="gallery-image"
      :style="{ backgroundImage: `url(${image})` }"
    ></div>
    <div id="image-main"></div>
  </div>
</template>

<style lang="sass">
  @import '../assets/sass/variables'

#main-content
  display: grid
  grid-template-areas: "image-0 image-1 image-2" "image-main image-main image-main" "image-5 image-4 image-3"
  grid-template-columns: 1fr 1fr 1fr
  grid-template-rows: calc($base-spacing * 2) 1fr calc($base-spacing * 2)
  gap: calc($base-spacing / 4)
  height: 100%
  width: 100%

  div
    height: 100%
    width: 100%
    border-radius: 1rem
    background-size: cover
    background-position: center

    &.gallery-image
      position: relative
      opacity: 0.5
      overflow: hidden
      transition: 200ms ease
      transition-property: opacity, transform

      &:hover
        opacity: 0.75
        transform: scale(0.9)

        &::after
          opacity: 0.33

      &::after
        content: ''
        position: absolute
        top: 0
        left: 0
        height: 100%
        width: 100%
        background-color: $primary-color
        opacity: 0.5
        transition: 200ms ease
        transition-property: opacity

  #image-0
    grid-area: image-0

  #image-1
    grid-area: image-1

  #image-2
    grid-area: image-2

  #image-3
    grid-area: image-3

  #image-4
    grid-area: image-4

  #image-5
    grid-area: image-5

  #image-main
    grid-area: image-main
    min-height: 400px
</style>
