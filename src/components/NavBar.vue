<script setup>
import { onMounted } from 'vue';

const props = defineProps({
  links: Array,
});
</script>

<template>
  <nav>
    <ul>
      <li v-for="link in props.links">
        <a :href="link.href"
          ><span v-html="link.icon"> </span>
          <div>
            <span v-html="link.href"></span>
          </div>
        </a>
      </li>
    </ul>
  </nav>
</template>

<style scoped lang="sass">
$transition-time: 250ms
$base-spacing: 12px
$large1-spacing: 18px
$large2-spacing: 24px
$large3-spacing: 36px
$large4-spacing: 48px

nav
  ul
    display: flex
    gap: calc(($large1-spacing + $base-spacing) * 2)
    justify-content: center
    align-content: center
    list-style: none
    width: min-content
    padding: calc($base-spacing * 6.5) calc($base-spacing * 4)

    li
      position: relative

      &:nth-of-type(odd)
        a
          transform: translate(-50%, -50%) rotate(-45deg)
          margin-top: calc(($large1-spacing + $base-spacing) * -1)

          &:hover
            transform: translate(-50%, -50%) rotate(-45deg) scale(1.15)

          > span
            transform: rotate(45deg)

        div
          top: 50%
          transform: translate(-50%, -50%) rotate(45deg)
          background: linear-gradient(to top, transparent 50%, #145577 50%)

      &:nth-of-type(even)
        a
          transform: translate(-50%, -50%) rotate(45deg)
          margin-top: calc($large1-spacing + $base-spacing)

          &:hover
            transform: translate(-50%, -50%) rotate(45deg) scale(1.15)

          > span
            transform: rotate(-45deg)

        div
          top: 50%
          transform: translate(-50%, -50%) rotate(-45deg)
          background: linear-gradient(to bottom, transparent 50%, #145577 50%)

          span
            align-self: flex-end

      a
        position: absolute
        top: 50%
        left: 50%
        display: flex
        justify-content: center
        align-content: center
        height: calc($large3-spacing * 2)
        width: calc($large3-spacing * 2)
        border-radius: $base-spacing
        color: rgb(215 215 215)
        background-color: #145577
        text-decoration: none
        filter: drop-shadow(0 0 0 rgba(0, 0, 0, 0.3))
        transition: transform $transition-time ease, filter $transition-time ease

        &:hover
          filter: drop-shadow(0 0 $base-spacing rgba(0, 0, 0, 0.3))

          div
            height: calc($large4-spacing * 3)
            color: rgb(215 215 215)
            transition: height $transition-time ease, color $transition-time ease

        > span
          font-size: 1.5rem
          align-self: center

      div
        position: absolute
        display: flex
        justify-content: center
        left: 50%
        height: 0
        width: calc($large4-spacing * 2 - 4px)
        padding: $base-spacing 0
        border-radius: $base-spacing
        color: transparent
        z-index: -1
        pointer-events: none
        transition: height $transition-time ease, color calc($transition-time / 4) ease

        span
          font-size: 0.8rem
          font-weight: 500
          text-transform: uppercase
</style>
