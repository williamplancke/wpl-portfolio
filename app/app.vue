<script setup lang="ts">
useHead({
  htmlAttrs: { lang: 'en' },
  meta: [
    { name: 'viewport', content: 'width=device-width, initial-scale=1' },
    { name: 'theme-color', content: '#f3f1ea' }
  ],
  link: [{ rel: 'icon', href: '/favicon.ico' }]
})

const title = 'William Plancke — Data Scientist'
const description = 'Portfolio of data science student William Plancke, showing off various projects he has worked on throughout his academic career.'

useSeoMeta({
  title,
  description,
  ogTitle: title,
  ogDescription: description,
  twitterCard: 'summary'
})
</script>

<template>
  <NuxtPage />
</template>
