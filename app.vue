<template>
  <div class="scroll-smooth">
    <!-- <DevOnly>
      <div class="bg-red-500 text-white p-1 text-center">
        You are currently in DEV mode
      </div>
    </DevOnly> -->
    <NavBar />
    <NuxtPage />
  </div>
</template>

<script setup lang="ts">

useHead({
  title: 'Qodesquare Technologies',
  meta: [
    {
      name: 'description',
      content: 'Your website description here',
    },
    {
      name: 'keywords',
      content: 'Code, Tech, consulting, Nigeria, Best Tech consulting, Software Development, Web Development, Mobile App Development',  
    },
    {
      name: 'author',
      content: 'Qodesuare Technologies',
    },
    {
      property: 'og:title',
      content: 'Qodesquare Technologies',
    },
    {
      property: 'og:description',
      content: 'Your website description here',
    },
    {
      property: 'og:type',
      content: 'website',
    },
    {
      property: 'og:url',
      content: 'https://www.qodesquare.com',
    },
    {
      property: 'og:image',
      content: 'https://www.yourwebsite.com/image.jpg',
    },
    {
      name: 'twitter:card',
      content: 'summary_large_image',
    },
    {
      name: 'twitter:title',
      content: 'Qodesquare Technologies',
    },
    {
      name: 'twitter:description',
      content: 'Your website description here',
    },
    {
      name: 'twitter:image',
      content: 'https://www.yourwebsite.com/image.jpg',
    },
  ],
});
</script>