<script setup>
import { onMounted, reactive } from 'vue';
import PageSection from './components/PageSection.vue';
import PageTitle from './components/PageTitle.vue';
import IntroSection from './components/IntroSection.vue';

const state = reactive({ sectionHeight: '' });

function setSectionHeight() {
  state.sectionHeight = window.innerHeight + 'px';
  console.log(state.sectionHeight);
}

onMounted(() => {
  setSectionHeight();

  window.addEventListener('resize', () => {
    setSectionHeight();
  });

  /* const cursorInner = document.getElementById('cursor-inner');
  const cursorOuter = document.getElementById('cursor-outer');
  let mouseX = 0;
  let mouseY = 0;
  let xp = 0;
  let yp = 0;
  window.onmousemove = (e) => {
    cursorInner.style.transform = `translate(${e.clientX}px, ${e.clientY}px)`;
    mouseX = e.clientX - 10;
    mouseY = e.clientY - 10;
  };
  setInterval(function () {
    xp += (mouseX - xp) / 6;
    yp += (mouseY - yp) / 6;
    cursorOuter.style.transform =
      'translateX(' + (xp - 18) + 'px) translateY(' + (yp - 14) + 'px)';
  }, 5); */
});
</script>

<template>
  <IntroSection :sectionHeight="state.sectionHeight"></IntroSection>
  <PageSection :sectionHeight="state.sectionHeight">
    <PageTitle mainText="Projects"></PageTitle>
  </PageSection>
  <PageSection :sectionHeight="state.sectionHeight">
    <PageTitle mainText="Education"></PageTitle>
  </PageSection>
  <PageSection :sectionHeight="state.sectionHeight">
    <PageTitle mainText="Work"></PageTitle>
  </PageSection>
  <PageSection :sectionHeight="state.sectionHeight">
    <PageTitle mainText="Skills"></PageTitle>
  </PageSection>
  <PageSection :sectionHeight="state.sectionHeight">
    <PageTitle mainText="Hobbies"></PageTitle>
  </PageSection>
  <PageSection :sectionHeight="state.sectionHeight">
    <PageTitle mainText="CV / Resume"></PageTitle>
  </PageSection>
  <PageSection :sectionHeight="state.sectionHeight">
    <PageTitle mainText="Contact"></PageTitle>
  </PageSection>
</template>

<!-- <style scoped lang="sass">
  @import "./assets/sass/variables"

#section-1
  display: flex
  flex-direction: row
  gap: $base-spacing

  .page-div-left, .page-div-right
    display: flex
    flex-direction: column
    width: 100%

  .page-div-left
    width: min-content

  @media only screen and (max-width: 1024px)
    flex-direction: column

    .page-div-left, .page-div-right
      width: 100%

    nav
      margin-left: auto
      margin-right: auto
      transform: scale(0.8)
</style> -->
