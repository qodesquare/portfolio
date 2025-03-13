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
    title: "Qodesquare Technologies",
    meta: [
      {
        name: "robots",
        content: "index, follow",
      },
      {
        name: "viewport",
        content: "width=device-width, initial-scale=1",
      },
      {
        name: "description",
        content:
          "Qodesquare specializes in software development, digital transformation, and IT consulting, helping businesses scale, optimize, and thrive. 🚀 Ideate. Innovate. Accelerate",
      },
      {
        name: "keywords",
        content:
          "Code, Tech, consulting, Nigeria, Best Tech consulting, Software Development, Web Development, Mobile App Development",
      },
      {
        name: "author",
        content: "Qodesuare Technologies",
      },
      {
        property: "og:title",
        content: "Qodesquare Technologies",
      },
      {
        property: "og:description",
        content: "Qodesquare specializes in software development, digital transformation, and IT consulting, helping businesses scale, optimize, and thrive. 🚀 Ideate. Innovate. Accelerate",
      },
      {
        property: "og:type",
        content: "website",
      },
      {
        property: "og:url",
        content: "https://www.qodesquare.com",
      },
      {
        property: "og:image",
        content: "https://www.qodesquare.com/q_white_logo.png",
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
        content: 'Qodesquare specializes in software development, digital transformation, and IT consulting, helping businesses scale, optimize, and thrive. 🚀 Ideate. Innovate. Accelerate',
      },
      {
        name: 'twitter:image',
        content: 'https://www.qodesquare.com/q_white_logo.png',
      },
    ],
  });
</script>
