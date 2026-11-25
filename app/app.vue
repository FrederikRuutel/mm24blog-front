<script setup lang="ts">
import { ElButton } from 'element-plus';

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
        <ElButton v-for="link in links" :key="link.to" :tag="NuxtLink" :to="link.to"
          :type="route.path === link.to ? 'primary' : 'default'">{{ link.label }}</ElButton>
        <ElButton tag="a" :href="repo">GitHub</ElButton>
      </UContainer>
    </header>
    <NuxtRouteAnnouncer />
    <UContainer as="main" class="py-6">
      <NuxtPage />
    </UContainer>
  </UApp>
</template>
