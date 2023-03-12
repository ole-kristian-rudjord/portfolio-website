<script setup>
// import { reactive, onMounted } from 'vue';

import { onMounted } from 'vue';

// const state = reactive({ sectionHeight: 0 });

// function setSectionHeight() {
//   state.sectionHeight = window.innerHeight;
//   console.log(state.sectionHeight);
// }

// onMounted(() => {
//   setSectionHeight();

//   window.addEventListener('resize', () => {
//     setSectionHeight();
//   });
// });

const props = defineProps({
  sectionHeight: String,
});
onMounted(() => {
  console.log(props.sectionHeight);
});
</script>

<template>
  <!-- <section :style="{ minHeight: state.sectionHeight + 'px' }"> -->
  <section :style="{ minHeight: `${props.sectionHeight}` }">
    <slot></slot>
  </section>
</template>

<style scoped lang="sass">
  @import "../assets/sass/variables"

section
  padding: $base-spacing
</style>
