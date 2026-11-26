<script setup lang="ts">
import { ElMenu, ElMenuItem } from 'element-plus';

const route = useRoute();
const links = [
  { label: 'Postitused', to: '/' },
  { label: 'Blogist', to: '/about' },
];
</script>

<template>
  <UApp>
    <header class="blog-header">
      <UContainer as="nav" class="blog-nav" aria-label="Põhimenüü">
        <strong>MM24 blogi</strong>
        <ElMenu :default-active="route.path" mode="horizontal" :ellipsis="false" class="blog-menu">
          <ElMenuItem v-for="link in links" :key="link.to" :index="link.to">
            <NuxtLink :to="link.to" @keydown.enter.stop>{{ link.label }}</NuxtLink>
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
