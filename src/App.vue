<script setup>
import { onMounted, reactive } from 'vue';
import PageSection from './components/PageSection.vue';
import PageTitle from './components/PageTitle.vue';
import IntroSection from './components/IntroSection.vue';
import DottedBackground from './components/DottedBackground.vue';

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

  document.documentElement.style.setProperty('--highlight-color', '#1191d6');

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
  <DottedBackground></DottedBackground>
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

<style lang="sass">
@import "./assets/sass/variables"
</style>
