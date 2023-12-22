<template>
  <div class="flex container max-w-sm mx-auto items-center justify-center mt-5 border-solid border-b-2 border-black mb-4">
    <footer>
      <ul class="flex items-center gap-6 text-sm ">
        <li v-for="link in footer" :key="link.name">
          <NuxtLink :to="link.path">
            {{ link.name }}
          </NuxtLink>
        </li>
      </ul>
    </footer>
  </div>
</template>

<script setup lang="ts">
import footerData from '~/src/userFooter.json'

type FooterItem = {
  name: string;
  path: string;
};

interface FooterData {
  footer: FooterItem[];
}

const footer = ref<FooterItem[]>((footerData as FooterData).footer)
</script>
