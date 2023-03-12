<script setup>
import PageSection from './PageSection.vue';
import PageTitle from './PageTitle.vue';
import NavBar from './NavBar.vue';
import MainGallery from './MainGallery.vue';

const props = defineProps({ sectionHeight: String });

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
</script>

<template>
  <PageSection :sectionHeight="props.sectionHeight">
    <div class="page-div-left">
      <PageTitle
        color="#1191d6"
        smallText="Hi, my name is"
        mainText="Ole Kristian Rudjord"
      ></PageTitle>
      <p>
        I am in my 4th semester towards a bachelor's degree in Applied Computer
        Science at OsloMet where I also work as a teaching assistant. I am
        passionate about web-development and really focused on learning more
        about web-technologies and improving my skills in all areas related to
        tech!
      </p>
      <p>
        To further develop my skills, I love working on projects outside of
        school. Amongst them is a website about gaming-mice (very nerdy stuff, I
        know) that I started in the beginning of 2022 to learn the basics of
        JavaScript. This eventually turned into
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
    <div class="page-div-right">
      <MainGallery :height="props.sectionHeight"></MainGallery>
    </div>
  </PageSection>
</template>

<style scoped lang="sass">
@import "../assets/sass/variables"

section
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
</style>
