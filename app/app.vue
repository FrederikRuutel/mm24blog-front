<script setup lang="ts">
import { NButton } from 'naive-ui';

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
        <NuxtLink v-for="link in links" :key="link.to" v-slot="{ href, navigate, isExactActive }" :to="link.to" custom>
          <NButton tag="a" :href="href" :type="isExactActive ? 'primary' : 'default'"
            :aria-current="isExactActive ? 'page' : undefined" @click="navigate">{{ link.label }}</NButton>
        </NuxtLink>
        <NButton tag="a" :href="repo">GitHub</NButton>
      </UContainer>
    </header>
    <NuxtRouteAnnouncer />
    <UContainer as="main" class="py-6">
      <NuxtPage />
    </UContainer>
  </UApp>
</template>
