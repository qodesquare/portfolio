<template>
  <section
    class="px-4 mx-auto mb-36"
    :class="{
      container: container,
    }"
  >
    <slot></slot>
  </section>
</template>

<script setup lang="ts">
  defineProps({
    container: {
      type: Boolean,
      default: true,
    },
  });
</script>

<style scoped></style>
