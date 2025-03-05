<script setup lang="ts">
  import type { HTMLAttributes } from "vue";
  import { cn } from "@/lib/utils";

  const props = defineProps({
    class: {
      type: String,
      default: "",
    },
    is: {
      type: String,
      default: "div",
    },
  });
</script>

<template>
  <component
    :is="is"
    :class="
      cn('rounded-xl border bg-card text-card-foreground shadow', props.class)
    "
  >
    <slot />
  </component>
</template>
