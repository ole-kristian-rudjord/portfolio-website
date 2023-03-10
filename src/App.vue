<script setup>
import { reactive } from 'vue';
import { createDOMCompilerError } from '@vue/compiler-dom';
import { onMounted } from 'vue';
import PageSection from './components/PageSection.vue';
import PageTitle from './components/PageTitle.vue';
import ParagraphComponent from './components/ParagraphComponent.vue';
import NavBar from './components/NavBar.vue';

// const state = reactive({ sectionHeights: [] });

// function updateSectionHeights() {
//   const heights = [];
//   document.querySelectorAll('section').forEach((a) => {
//     heights.push(a.clientHeight);
//   });
//   state.sectionHeights = heights;
// }

// let sectionCounter = 0;

const NavBarLinks = [
  {
    href: 'intro',
    icon: '<i class="fa-solid fa-house"></i>',
  },
  {
    href: 'projects',
    icon: '<i class="fa-solid fa-code"></i>',
  },
  {
    href: 'education',
    icon: '<i class="fa-solid fa-graduation-cap"></i>',
  },
  {
    href: 'work',
    icon: '<i class="fa-solid fa-briefcase"></i>',
  },
  {
    href: 'skills',
    icon: '<i class="fa-brands fa-square-js"></i>',
  },
  {
    href: 'hobbies',
    icon: '<i class="fa-solid fa-heart"></i>',
  },
  {
    href: 'contact',
    icon: '<i class="fa-solid fa-envelope"></i>',
  },
];

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

  // updateSectionHeights();

  // window.addEventListener('resize', () => {
  //   updateSectionHeights();
  // });
});
</script>

<template>
  <PageSection color="#1191d6">
    <div class="page-div-left">
      <PageTitle
        color="#1191d6"
        smallText="Hi, my name is"
        mainText="Ole Kristian Rudjord"
      ></PageTitle>
      {{ sectionHeights }}
      <p>
        Who am I? A student in my 4th semester towards a bachelor's degree in
        Applied Computer Science at OsloMet where I also work as a teaching
        assistant. I am passionate about web-development and really focused on
        learning more about web-technologies and improving my skills in all
        areas related to tech!
      </p>
      <p>
        I like working on projects outside of school to further develop my
        skills and explore new technologies. Amongst them is a gaming mouse
        website (very nerdy stuff, I know) that I started in the beginning of
        2022 to learn the basics of JavaScript. This eventually turned into
        <a href="https://www.eloshapes.com/">EloShapes.com</a>, a full-fledged
        website with more than 70 000 monthly visits.
      </p>
      <p>
        Outside of studies and web-related projects, I love playing video-games.
        My all time favorites include Pokemon Platinum, Destiny, and TitanFall
        2. Another hobby of mine includes, as you might have guessed,
        gaming-mice. I also like running and working out.
      </p>
      <NavBar :links="NavBarLinks"></NavBar>
    </div>
    <div class="page-div-right"></div>
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

<style scoped lang="sass">
.page-div-left, .page-div-right
  display: flex
  flex-direction: column
  height: 100%
  width: 50%

  &::last-child
    margin-top: auto

p
  margin-bottom: 1rem
  line-height: 1.5
  font-weight: 400
  text-align: justify
  color: rgb(215, 215, 215)

  a
    position: relative
    color: unset
    text-decoration: none

    &::after
      content: ''
      position: absolute
      bottom: 0
      left: 0
      height: 6px
      width: 100%
      border-radius: 1px
      background-color: purple
      outline: 0 solid purple
      opacity: 0.6
      z-index: -1
      transition: height 150ms ease, outline-width 75ms ease

    &:hover:after
      height: 100%
      outline-width: 2px
</style>
