<script setup lang="ts">
  import { usePoemStore } from "@/shared/stores";
  const poemStore = usePoemStore();
</script>

<template>
  <div class="flex justify-center mt-10">
    <div class="flex flex-col gap-10">
      <div
        class="quatrain"
        v-for="quatrain in poemStore.quatrains"
        :key="quatrain.id"
        :id="`quatrain-${quatrain.id}`"
      >
        <p
          v-for="line in quatrain.quatrain"
          :key="line"
        >
          {{ line }}
        </p>
      </div>
    </div>
  </div>
</template>

<style lang="css" scoped>
  .quatrain {
    &.quatrain_hide {
      @apply hidden;
    }
    p {
      @apply text-xl;
    }
    p:nth-child(even) {
      @apply ml-10;
    }
  }
</style>
