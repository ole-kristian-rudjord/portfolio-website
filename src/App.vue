<script setup>
import { onMounted } from 'vue';
import PageSection from './components/PageSection.vue';
import PageTitle from './components/PageTitle.vue';
import NavBar from './components/NavBar.vue';

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
    href: 'CV / resume',
    icon: '<i class="fa-solid fa-file-lines"></i>',
  },
  {
    href: 'contact',
    icon: '<i class="fa-solid fa-envelope"></i>',
  },
];

onMounted(() => {
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
  <PageSection color="#1191d6" id="section-1">
    <div class="page-div-left">
      <PageTitle
        color="#1191d6"
        smallText="Hi, my name is"
        mainText="Ole Kristian Rudjord"
      ></PageTitle>
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
        website with more than <span class="nowrap">70 000</span> monthly
        visits.
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
  <PageSection>
    <PageTitle mainText="Skills"></PageTitle>
  </PageSection>
  <PageSection>
    <PageTitle mainText="Hobbies"></PageTitle>
  </PageSection>
  <PageSection>
    <PageTitle mainText="CV / Resume"></PageTitle>
  </PageSection>
  <PageSection>
    <PageTitle mainText="Contact"></PageTitle>
  </PageSection>
</template>

<style scoped lang="sass">
  @import "./assets/sass/variables"

#section-1
  display: flex
  flex-direction: row
  gap: $base-spacing

  .page-div-left, .page-div-right
    display: flex
    flex-direction: column
    width: 50%

  @media only screen and (max-width: 1024px)
    flex-direction: column

    .page-div-left, .page-div-right
      width: 100%

    nav
      margin-left: auto
      margin-right: auto
      transform: scale(0.8)
</style>
