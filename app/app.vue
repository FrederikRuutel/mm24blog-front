<script setup lang="ts">
import Menubar from 'primevue/menubar';

const links = [
  { label: 'Postitused', to: '/' },
  { label: 'Cats', to: '/cats' },
  { label: 'Kittens', to: '/kittens' },
  { label: 'Nuustik', to: '/kittens/nuustik' },
  { label: 'Miisu', to: '/kittens/miisu' },
];
</script>

<template>
  <UApp>
    <header class="blog-header">
      <UContainer as="nav" class="blog-nav" aria-label="Põhimenüü">
        <strong>MM24 blogi</strong>
        <Menubar :model="links" breakpoint="480px" class="blog-menu">
          <template #item="{ item, props }">
            <NuxtLink :to="item.to" v-bind="props.action">{{ item.label }}</NuxtLink>
          </template>
        </Menubar>
      </UContainer>
    </header>
    <NuxtRouteAnnouncer />
    <UContainer as="main" class="py-6">
      <NuxtPage />
    </UContainer>
  </UApp>
</template>
