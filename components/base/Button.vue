<template>
  <div
    v-if="!link"
    class="inline-flex cursor-pointer place-content-center rounded border border-primary py-2 px-4 font-sans text-primary hover:bg-primary/10"
  >
    <slot>Click</slot>
  </div>
  <a
    v-else-if="external"
    :href="disabled ? null : link"
    class="inline-flex place-content-center rounded border border-primary py-2 px-4 font-sans text-primary hover:bg-primary/10"
    :class="disabled ? 'disabled' : ''"
  >
    <slot>Click</slot>
  </a>
  <nuxt-link
    v-else
    :href="disabled ? null : link"
    class="inline-flex place-content-center rounded border border-primary py-2 px-4 font-sans text-primary hover:bg-primary/10"
    :class="disabled ? 'disabled-blur' : ''"
  >
    <slot>Click</slot>
  </nuxt-link>
</template>

<script setup>
defineProps(["link", "disabled", "external"]);
</script>
