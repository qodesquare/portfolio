<template>
  <section
    v-bind="$attrs"
    class="px-4 mx-auto mb-36 last-of-type:mb-16 scroll-mt-28"
    :class="
      cn(
        {
          container: container,
        },
        props.class
      )
    "
  >
    <slot></slot>
  </section>
</template>

<script setup lang="ts">
  import { cn } from "@/lib/utils";
  import type { HTMLAttributes } from "vue";

  const props = withDefaults(
    defineProps<{
      class?: HTMLAttributes["class"];
      container?: boolean;
    }>(),
    {
      class: "",
      container: true,
    }
  );
</script>

<style scoped></style>
