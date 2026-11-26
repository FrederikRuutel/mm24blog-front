<script setup lang="ts">
import { NMenu } from 'naive-ui';

const NuxtLink = resolveComponent('NuxtLink');
const route = useRoute();
const links = [
  { label: 'Postitused', to: '/' },
  { label: 'Blogist', to: '/about' },
];

const options = links.map(link => ({
  key: link.to,
  label: () => h(NuxtLink, { to: link.to }, () => link.label),
}));
</script>

<template>
  <UApp>
    <header class="blog-header">
      <UContainer as="nav" class="blog-nav" aria-label="Põhimenüü">
        <strong>MM24 blogi</strong>
        <NMenu :value="route.path" :options="options" mode="horizontal" class="blog-menu" />
      </UContainer>
    </header>
    <NuxtRouteAnnouncer />
    <UContainer as="main" class="py-6">
      <NuxtPage />
    </UContainer>
  </UApp>
</template>
