<script setup lang="ts">
  interface props {
    checked: boolean;
  }

  const props = defineProps<props>();
</script>

<template>
  <input
    type="checkbox"
    class="appearance-none w-6 aspect-square border-[3px] border-black checked:bg-black cursor-pointer"
    :checked="props.checked"
  />
</template>
