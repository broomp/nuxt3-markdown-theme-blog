<template>
  <nav>
    <div class="flex container max-w-sm mx-auto items-center justify-center mt-5 border-solid border-b-2 border-black">
      <ul class="flex items-center gap-6 text-sm ">
        <li v-for="link in navigation" :key="link.name">
          <NuxtLink :to="link.path">
            {{ link.name }}
          </NuxtLink>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script setup lang="ts">
import navigationData from '~/src/userNav.json'

type NavigationItem = {
  name: string;
  path: string;
};

interface NavigationData {
  nav: NavigationItem[];
}

const navigation = ref<NavigationItem[]>((navigationData as NavigationData).nav)
</script>
