<script setup>
import DiamondShape from './DiamondShape.vue';
</script>

<template>
  <div id="main-content">
    <DiamondShape
      id="image-1"
      backgroundImageURL="https://media.licdn.com/dms/image/D4E03AQFd9gaMe4gVXQ/profile-displayphoto-shrink_800_800/0/1634923935396?e=2147483647&v=beta&t=tYbMJ2-ymrgQNpenCnJbmyypQHF8HHyr55ACPOC4A9s"
    ></DiamondShape>
    <DiamondShape
      id="image-2"
      backgroundImageURL="https://media.licdn.com/dms/image/D4E03AQFd9gaMe4gVXQ/profile-displayphoto-shrink_800_800/0/1634923935396?e=2147483647&v=beta&t=tYbMJ2-ymrgQNpenCnJbmyypQHF8HHyr55ACPOC4A9s"
    ></DiamondShape>
    <DiamondShape
      id="image-3"
      backgroundImageURL="https://media.licdn.com/dms/image/D4E03AQFd9gaMe4gVXQ/profile-displayphoto-shrink_800_800/0/1634923935396?e=2147483647&v=beta&t=tYbMJ2-ymrgQNpenCnJbmyypQHF8HHyr55ACPOC4A9s"
    ></DiamondShape>
    <DiamondShape
      id="image-4"
      backgroundImageURL="https://media.licdn.com/dms/image/D4E03AQFd9gaMe4gVXQ/profile-displayphoto-shrink_800_800/0/1634923935396?e=2147483647&v=beta&t=tYbMJ2-ymrgQNpenCnJbmyypQHF8HHyr55ACPOC4A9s"
    ></DiamondShape>
    <DiamondShape
      id="image-5"
      backgroundImageURL="https://media.licdn.com/dms/image/D4E03AQFd9gaMe4gVXQ/profile-displayphoto-shrink_800_800/0/1634923935396?e=2147483647&v=beta&t=tYbMJ2-ymrgQNpenCnJbmyypQHF8HHyr55ACPOC4A9s"
    ></DiamondShape>
    <DiamondShape
      id="image-6"
      backgroundImageURL="https://media.licdn.com/dms/image/D4E03AQFd9gaMe4gVXQ/profile-displayphoto-shrink_800_800/0/1634923935396?e=2147483647&v=beta&t=tYbMJ2-ymrgQNpenCnJbmyypQHF8HHyr55ACPOC4A9s"
    ></DiamondShape>
    <DiamondShape
      id="image-7"
      backgroundImageURL="https://media.licdn.com/dms/image/D4E03AQFd9gaMe4gVXQ/profile-displayphoto-shrink_800_800/0/1634923935396?e=2147483647&v=beta&t=tYbMJ2-ymrgQNpenCnJbmyypQHF8HHyr55ACPOC4A9s"
    ></DiamondShape>
  </div>
</template>

<style scoped lang="sass">
  @import '../assets/sass/variables'

#main-content
  display: grid
  grid-template-areas: "image1 image2 image3" "image7 image7 image7" "image6 image5 image4"
  height: 100%
  width: 100%
  outline: 3px dotted red

  #image-1
    grid-area: image1

  #image-2
    grid-area: image2

  #image-3
    grid-area: image3

  #image-4
    grid-area: image4

  #image-5
    grid-area: image5

  #image-6
    grid-area: image6

  #image-7
    grid-area: image7
</style>
