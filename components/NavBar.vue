<template>
  <nav
    class="p-6 sticky top-0 bg-white/80 z-40 md:backdrop-blur"
    :class="{ 'backdrop-blur': !isOpen }"
  >
    <div class="container mx-auto">
      <div class="flex items-center justify-between">
        <NuxtLink to="/"><AppLogo /></NuxtLink>

        <ul class="items-center gap-8 hidden md:flex">
          <li
            v-for="link in appInfo.navLinks"
            :key="link.url"
            class="w-full group transition-all duration-500"
          >
            <NuxtLink
              :to="link.url"
              class="group-hover:underline underline-offset-4 decoration-2"
              >{{ link.name }}
            </NuxtLink>
          </li>
        </ul>

        <div class="hidden md:block">
          <Button>Book a session</Button>
        </div>

        <HambugerMenu
          class="md:hidden"
          :isOpen="isOpen"
          :toggleMenu="toggleMenu"
        >
          <template #menu-items>
            <ul class="flex items-start gap-8 flex-col text-xl/8 font-medium">
              <li v-for="link in appInfo.navLinks" :key="link.url">
                <NuxtLink :to="link.url">{{ link.name }}</NuxtLink>
              </li>

              <li><Button>Book a session</Button></li>
            </ul>
          </template>
        </HambugerMenu>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
  import Button from "./ui/button/Button.vue";
  import HambugerMenu from "./ui/hamburgermenu/HambugerMenu.vue";

  const appInfo = ref({
    logo: "/imgs/logo.svg",
    navLinks: [
      { name: "Home", url: "/" },
      { name: "Services", url: "/services" },
      { name: "Careers", url: "/careers" },
    ],
  });

  const isOpen = ref(false);
  const toggleMenu = () => {
    isOpen.value = !isOpen.value;
  };
</script>

<style scoped></style>
