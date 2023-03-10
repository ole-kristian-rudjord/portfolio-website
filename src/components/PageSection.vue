<script setup>
import { reactive, onMounted } from 'vue';

const state = reactive({ sectionHeight: 0 });

function setSectionHeight() {
  state.sectionHeight = window.innerHeight;
  console.log(state.sectionHeight);
}

onMounted(() => {
  setSectionHeight();
});

defineProps({
  color: String,
});
</script>

<template>
  <section :style="{ height: state.sectionHeight + 'px' }">
    <div>
      <slot></slot>
    </div>
  </section>
</template>

<style scoped lang="sass">
section
  padding: 4rem

  div
    display: flex
    flex-direction: row
    gap: 4rem
    height: 100%
</style>
