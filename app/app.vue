<script setup lang="ts">
import { ElMenu, ElMenuItem } from 'element-plus';

const route = useRoute();
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
        <ElMenu router :default-active="route.path" mode="horizontal" :ellipsis="false" class="blog-menu">
          <ElMenuItem v-for="link in links" :key="link.to" :index="link.to" :route="link.to"
            :aria-current="route.path === link.to ? 'page' : undefined">
            <NuxtLink :to="link.to" tabindex="-1" @click.stop>{{ link.label }}</NuxtLink>
          </ElMenuItem>
        </ElMenu>
      </UContainer>
    </header>
    <NuxtRouteAnnouncer />
    <UContainer as="main" class="py-6">
      <NuxtPage />
    </UContainer>
  </UApp>
</template>
