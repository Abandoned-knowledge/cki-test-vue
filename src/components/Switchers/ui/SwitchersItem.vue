<script setup lang="ts">
  interface props {
    checked: boolean;
  }

  const props = defineProps<props>();
</script>

<template>
  <input
    type="checkbox"
    class="aspect-square w-6 cursor-pointer appearance-none border-[3px] border-black checked:bg-black"
    :checked="props.checked"
  />
</template>
