<template>
  <button class="relative group z-50" @click="toggleMenu" v-bind="$attrs">
    <div
      class="relative flex overflow-hidden items-center justify-center rounded w-[40px] h-[40px] transform transition-all duration-200"
    >
      <div
        class="flex flex-col justify-between w-[27px] h-[21px] transform transition-all duration-300 origin-center overflow-hidden"
      >
        <div
          class="bg-black h-[2.5px] w-[16px] rounded transform transition-all duration-300 origin-right"
          :class="{
            '-rotate-[45deg] translate-x-[5px] translate-y-[1px]': isOpen,
          }"
        ></div>
        <div
          class="bg-black h-[2.5px] w-[24px] rounded transform transition-all duration-300"
          :class="{ 'rotate-45': isOpen }"
        ></div>
        <div
          class="bg-black h-[2.5px] w-[10px] rounded transform transition-all duration-300 origin-left"
          :class="{
            '-rotate-[45deg] translate-x-[3.5px] translate-y-[0px]': isOpen,
          }"
        ></div>
      </div>
    </div>
  </button>

  <Transition
    enter-active-class="transition-opacity duration-500 ease-in-out"
    enter-from-class="opacity-0"
    enter-to-class="opacity-100"
    leave-active-class="transition-opacity duration-500 ease-in-out"
    leave-from-class="opacity-100"
    leave-to-class="opacity-0"
  >
    <Menu v-if="isOpen" v-slot:menu-items>
      <slot name="menu-items"></slot>
    </Menu>
  </Transition>
</template>

<script setup lang="ts">
  import { ref } from "vue";
  import Menu from "./Menu.vue";

  const props = defineProps({
    isOpen: Boolean,
    toggleMenu: Function,
  });
</script>

<style scoped></style>
