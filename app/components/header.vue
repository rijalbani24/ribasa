<template>
  <div class="flex items-center justify-between bg-[#7b5cff] p-2">
    <!-- Logo -->
    <div>
      <NuxtLink to="/">
        <img src="/logo-ribasa (1).png" alt="Logo" class="h-10 w-auto" />
      </NuxtLink>
    </div>

    <!-- Desktop Menu -->
    <div class="hidden lg:block">
      <UNavigationMenu
        arrow
        content-orientation="vertical"
        :items="items"
        :ui="{
          link: 'text-white px-4 py-2 rounded-md transition-colors duration-300 bg-transparent hover:bg-[#ffed31] hover:text-black data-[active=true]:!bg-[#ffed31] data-[active=true]:!text-black focus:!bg-[#ffed31] focus:!text-black active:!bg-[#ffed31] active:!text-black',
          item: 'text-black mx-2',
          content: 'bg-[#7b5cff] text-white'
        }"
      />
    </div>

    <!-- Mobile Hamburger -->
    <div class="lg:hidden">
      <button @click="toggleMobileMenu" class="text-white focus:outline-none" aria-label="Toggle menu">
        <svg
          v-if="!mobileMenuOpen"
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
        </svg>
        <svg
          v-else
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>
    </div>
  </div>

  <!-- Mobile Menu Fullscreen -->
  <transition name="fade">
    <div
      v-if="mobileMenuOpen"
      class="fixed inset-0 z-50 bg-[#7b5cff] flex flex-col p-6 space-y-6"
    >
      <!-- Top Bar: Logo + Close -->
      <div class="flex items-center justify-between">
        <NuxtLink to="/">
          <img src="/logo-ribasa (1).png" alt="Logo" class="h-10 w-auto" />
        </NuxtLink>

        <button
          @click="mobileMenuOpen = false"
          class="text-white focus:outline-none"
          aria-label="Close menu"
        >
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>

      <!-- Menu List -->
      <div class="flex flex-col space-y-4 mt-6">
        <NuxtLink
          v-for="item in items"
          :key="item.label"
          :to="item.to"
          class="block text-white px-4 py-3 rounded-md hover:bg-[#ffed31] hover:text-black transition-colors duration-300"
          @click="mobileMenuOpen = false"
          :class="{ '!bg-[#ffed31] !text-black': isActiveRoute((item as any).to) }"
          exact
        >
          {{ item.label }}
        </NuxtLink>
      </div>
    </div>
  </transition>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { useRoute } from 'vue-router'
import type { NavigationMenuItem } from '@nuxt/ui'

const items = ref<NavigationMenuItem[]>([
  { label: 'Home', to: '/' },
  { label: 'Project', to: '/project' },
  { label: 'Kontak', to: '/contact' }
])

const mobileMenuOpen = ref(false)
const route = useRoute()

function toggleMobileMenu() {
  mobileMenuOpen.value = !mobileMenuOpen.value
}

function isActiveRoute(path: string) {
  return route.path === path
}
</script>

<style>
[data-reka-collection-item]::before {
  background: transparent !important;
}

/* Fade in/out animation */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.fade-enter-to,
.fade-leave-from {
  opacity: 1;
}
</style>
