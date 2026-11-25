<script setup lang="ts">
import type { BlogPostProps } from '@nuxt/ui';

const route = useRoute();
const posts = ref<BlogPostProps[]>([]);
const page = ref(1);
const total = ref(0);
const perPage = ref(16);
const loadError = ref(false);

interface PostsResponse {
  current_page: number;
  total: number;
  per_page: number;
  data: { id: number; title: string; snippet: string; images?: { path: string }[]; created_at: string }[];
}

async function getPosts(p: number) {
  loadError.value = false;
  try {
    const data = await $fetch<PostsResponse>('http://localhost:8000/api/posts', {
      query: { page: p },
      headers: { accept: 'application/json' },
    });
    page.value = data.current_page;
    total.value = data.total;
    perPage.value = data.per_page;
    posts.value = data.data.map(post => ({
      title: post.title,
      description: post.snippet,
      image: post.images?.[0]?.path,
      date: post.created_at,
    }));
  } catch {
    posts.value = [];
    total.value = 0;
    loadError.value = true;
  }
}

onMounted(() => getPosts(Number(route.query.page) || 1));

function to(page: number) {
  return { query: { page } };
}
</script>

<template>
  <h1 class="mb-3 text-2xl font-semibold">Postitused</h1>
  <p v-if="loadError" role="status">Postitusi ei saanud laadida. Kontrolli, kas Laraveli API töötab.</p>
  <template v-else>
    <UPagination v-if="total > perPage" v-model:page="page" :to="to" :items-per-page="perPage"
      :total="total" show-edges :sibling-count="2" @update:page="getPosts" />
    <UBlogPosts class="lg:grid-cols-4">
      <UBlogPost v-for="(post, index) in posts" :key="index" v-bind="post" />
    </UBlogPosts>
  </template>
</template>
