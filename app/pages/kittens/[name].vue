<script setup lang="ts">
const route = useRoute();
const name = computed(() => String(route.params.name));
const title = computed(() => name.value.charAt(0).toUpperCase() + name.value.slice(1));
</script>

<template>
  <section>
    <h1 class="mb-3 text-2xl font-semibold">{{ title }}</h1>
    <p>See on kassipoja {{ title }} leht.</p>
    <NuxtLink to="/kittens" class="underline">Tagasi kassipoegade juurde</NuxtLink>
  </section>
</template>
