<script setup>
import { createDOMCompilerError } from '@vue/compiler-dom';
import { onMounted } from 'vue';
import PageSection from './components/PageSection.vue';
import PageTitle from './components/PageTitle.vue';
import ParagraphComponent from './components/ParagraphComponent.vue';

onMounted(() => {
  const cursorInner = document.getElementById('cursor-inner');
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
  }, 5);
});
</script>

<template>
  <PageSection color="#1191d6">
    <PageTitle
      color="#1191d6"
      smallText="Hi, my name is"
      mainText="Ole Kristian Rudjord"
    ></PageTitle>
    <ParagraphComponent
      mainText="Lorem ipsum dolor sit amet consectetur adipisicing elit. Est reprehenderit
      minus ad nostrum qui recusandae dolor. Ex pariatur velit distinctio sunt
      tempore cupiditate dicta similique possimus eius! Beatae, accusantium
      cupiditate. Lorem ipsum dolor sit amet consectetur adipisicing elit.
      Deleniti temporibus debitis maiores voluptates! Voluptates, et quod illum,
      quidem alias in libero reprehenderit beatae culpa sunt vero, ducimus
      tempore quaerat delectus."
    ></ParagraphComponent>
  </PageSection>
  <PageSection>
    <PageTitle mainText="Projects"></PageTitle>
  </PageSection>
  <PageSection>
    <PageTitle mainText="Education"></PageTitle>
  </PageSection>
  <PageSection>
    <PageTitle mainText="Work"></PageTitle>
  </PageSection>
</template>

<style scoped lang="sass"></style>
