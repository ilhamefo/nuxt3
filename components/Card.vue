<script setup lang="ts">
const props = defineProps({
  url: String,
});
</script>
<template>
  <div
    class="flex flex-col items-start justify-start ring-2 ring-black shadow-[8px_8px_0px_0px_rgb(39,39,37)] rounded-xl p-5 gap-3"
  >
    <div class="sm:mb-10 mb-3">
      <slot name="icon">icon here</slot>
    </div>

    <div class="text-2xl font-semibold">
      <slot name="title">title</slot>
    </div>

    <div class="text-lg text-slate-600 font-medium">
      <slot name="subtitle">subtitle</slot>
    </div>

    <a :href="props.url" target="_blank" class="flex items-center gap-3 mt-5">
      <span class="text-xl text-slate-900 font-semibold">
        <slot name="button">button</slot>
      </span>

      <IconsArrowLong />
    </a>
  </div>
</template>
