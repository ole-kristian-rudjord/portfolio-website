<script setup>
import { onMounted } from 'vue';
import DiamondShape from './DiamondShape.vue';

const props = defineProps({
  height: String,
});

let counter = 0;
function swapImages() {
  counter = counter % 6;

  let el1 = document.getElementById('image-6');
  let el2 = document.getElementById(`image-${counter}`);

  el1.id = `image-${counter}`;
  el2.id = 'image-6';

  counter++;
}

onMounted(() => {
  setInterval(swapImages, 5000);
});
</script>

<template>
  <div id="main-content">
    <DiamondShape
      id="image-0"
      backgroundImageURL="https://images.unsplash.com/photo-1546776310-eef45dd6d63c?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=810&q=80"
    ></DiamondShape>
    <DiamondShape
      id="image-1"
      backgroundImageURL="https://images.unsplash.com/photo-1534723328310-e82dad3ee43f?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8NHx8cm9ib3R8ZW58MHx8MHx8&auto=format&fit=crop&w=500&q=60"
    ></DiamondShape>
    <DiamondShape
      id="image-2"
      backgroundImageURL="https://images.unsplash.com/photo-1589254065909-b7086229d08c?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8NXx8cm9ib3R8ZW58MHx8MHx8&auto=format&fit=crop&w=500&q=60"
    ></DiamondShape>
    <DiamondShape
      id="image-3"
      backgroundImageURL="https://images.unsplash.com/photo-1601132359864-c974e79890ac?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTF8fHJvYm90fGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=500&q=60"
    ></DiamondShape>
    <DiamondShape
      id="image-4"
      backgroundImageURL="https://images.unsplash.com/photo-1580835239846-5bb9ce03c8c3?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTV8fHJvYm90fGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=500&q=60"
    ></DiamondShape>
    <DiamondShape
      id="image-5"
      backgroundImageURL="https://images.unsplash.com/photo-1555255707-c07966088b7b?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTd8fHJvYm90fGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=500&q=60"
    ></DiamondShape>
    <DiamondShape
      id="image-6"
      backgroundImageURL="https://media.licdn.com/dms/image/D4E03AQFd9gaMe4gVXQ/profile-displayphoto-shrink_800_800/0/1634923935396?e=2147483647&v=beta&t=tYbMJ2-ymrgQNpenCnJbmyypQHF8HHyr55ACPOC4A9s"
    ></DiamondShape>
  </div>
</template>

<style lang="sass">
  @import '../assets/sass/variables'

$gallery-width: calc(v-bind("props.height") * 0.4802561366)
$gallery-spacing: 1.25rem
$gallery-diamond-width: 8rem

#main-content
  position: relative
  display: grid
  height: 100%
  width: 100%
  max-width: $gallery-width
  margin: auto

  > div
    position: absolute
    opacity: 0.4
    transition: 350ms ease

  #image-0
    width: $gallery-diamond-width
    top: calc(50% - ($gallery-width / 2) - $gallery-spacing)
    transform: translateY(-50%) translateX(calc(-100% - $gallery-spacing))
    left: 50%

  #image-1
    width: $gallery-diamond-width
    top: calc(50% - ($gallery-width / 2) - $gallery-spacing)
    transform: translateY(calc(-100% - $gallery-spacing)) translateX(-50%)
    left: 50%

  #image-2
    width: $gallery-diamond-width
    top: calc(50% - ($gallery-width / 2) - $gallery-spacing)
    transform: translateY(-50%) translateX($gallery-spacing)
    left: 50%

  #image-3
    width: $gallery-diamond-width
    top: calc(50% + ($gallery-width / 2) + $gallery-spacing)
    transform: translateY(-50%) translateX($gallery-spacing)
    left: 50%

  #image-4
    width: $gallery-diamond-width
    top: calc(50% + ($gallery-width / 2) + $gallery-spacing)
    transform: translateY($gallery-spacing) translateX(-50%)
    left: 50%

  #image-5
    width: $gallery-diamond-width
    top: calc(50% + ($gallery-width / 2) + $gallery-spacing)
    transform: translateY(-50%) translateX(calc(-100% - $gallery-spacing))
    left: 50%

  #image-6
    width: 100%
    top: 50%
    transform: translateY(-50%) translateX(-50%)
    left: 50%
    opacity: 1
</style>
