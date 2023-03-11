<script setup>
import { reactive, onMounted } from 'vue';

const state = reactive({ sectionHeight: 0 });

function setSectionHeight() {
  state.sectionHeight = window.innerHeight;
  console.log(state.sectionHeight);
}

onMounted(() => {
  setSectionHeight();

  window.addEventListener('resize', () => {
    setSectionHeight();
  });
});

defineProps({
  color: String,
});
</script>

<template>
  <section :style="{ minHeight: state.sectionHeight + 'px' }">
    <!-- <div> -->
    <slot></slot>
    <!-- </div> -->
  </section>
</template>

<style scoped lang="sass">
  @import "../assets/sass/variables"

section
  padding: $base-spacing

  // div
  //   display: flex
  //   flex-direction: row
  //   gap: $base-spacing
  //   height: 100%
</style>
