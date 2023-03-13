<script setup>
const props = defineProps({ sectionHeight: String });

const projects = [
  {
    name: 'EloShapes',
    logo: '<i class="fa-solid fa-compact-disc"></i>',
    fromDate: 'Jan 2022',
    toDate: 'Now',
    paragraphs: [
      'EloShapes was launched on 08/20/2022, reaching more than 6500 users within 24 hours, now having an average of over 75 000 monthly visits.',
      'This is a passion project website that lets users compare the shapes and technical specifications of mice to help them find what might be their next purchase.',
      'The website hosts a database with over 280 mice which continues to evolve through me and the users adding and updating existing and upcoming products.',
    ],
    technologies: [
      { name: 'JavaScript', icon: '<i class="fa-solid fa-compact-disc"></i>' },
      { name: 'HTML', icon: '<i class="fa-solid fa-compact-disc"></i>' },
      { name: 'CSS', icon: '<i class="fa-solid fa-compact-disc"></i>' },
      { name: 'Java', icon: '<i class="fa-solid fa-compact-disc"></i>' },
      { name: 'SpringBoot', icon: '<i class="fa-solid fa-compact-disc"></i>' },
      { name: 'MongoDB', icon: '<i class="fa-solid fa-compact-disc"></i>' },
      { name: 'Heroku', icon: '<i class="fa-solid fa-compact-disc"></i>' },
      { name: 'GoDaddy', icon: '<i class="fa-solid fa-compact-disc"></i>' },
      { name: 'CloudFlare', icon: '<i class="fa-solid fa-compact-disc"></i>' },
      {
        name: 'Google Analytics',
        icon: '<i class="fa-solid fa-compact-disc"></i>',
      },
    ],
    images: [''],
  },
];
</script>

<template>
  <PageSection :sectionHeight="props.sectionHeight"></PageSection>
</template>

<style scoped lang="sass">
@import "../assets/sass/variables"
</style>
