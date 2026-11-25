<script setup lang="ts">
import Button from 'primevue/button';

const NuxtLink = resolveComponent('NuxtLink');
const route = useRoute();
const repo = 'https://github.com/Kasparsu/mm24blog-front';
const links = [
  { label: 'Avaleht', to: '/' },
  { label: 'Blogist', to: '/about' },
];
</script>

<template>
  <UApp>
    <header class="blog-header">
      <UContainer as="nav" aria-label="Põhimenüü" class="blog-nav">
        <strong>Blog</strong>
        <Button v-for="link in links" :key="link.to" :as="NuxtLink" :to="link.to"
          :label="link.label" :variant="route.path === link.to ? undefined : 'text'" />
        <Button as="a" :href="repo" label="GitHub" variant="text" />
      </UContainer>
    </header>
    <NuxtRouteAnnouncer />
    <UContainer as="main" class="py-6">
      <NuxtPage />
    </UContainer>
  </UApp>
</template>
