<template>
  <NuxtLink
    to="#"
    class="flex items-center p-3 rounded-full w-min hover:bg-gray-200 dark:hover:bg-dim-200 dark:text-white"
    :class="defaultTransition"
  >
    <div class="w-6 h-6 text-dark">
      <slot name="icon"></slot>
    </div>
    <div class="ml-4 text-xl hidden md:block" :class="textClasses">
      <slot name="name"></slot>
    </div>
  </NuxtLink>
</template>

<script setup lang="ts">
const { defaultTransition } = useTailwindConfig();

interface Props {
  active?: boolean;
}

const props = withDefaults(defineProps<Props>(), {
  active: false,
});

const textClasses = computed(() =>
  props.active ? "font-semibold" : "font-normal"
);
</script>

<style scoped></style>
