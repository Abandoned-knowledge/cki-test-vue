<script setup lang="ts">
  import { usePoemStore } from "@/shared/stores";
  const poemStore = usePoemStore();
</script>

<template>
  <main class="container flex justify-center mt-10">
    <div class="flex flex-col gap-10">
      <div
        class="quatrain"
        v-for="quatrain in poemStore.quatrains"
        :key="quatrain.id"
      >
        <p
          v-for="line in quatrain.quatrain"
          :key="line"
        >
          {{ line }}
        </p>
      </div>
    </div>
  </main>
</template>

<style lang="css" scoped>
  .quatrain {
    p {
      @apply text-xl;
    }
    p:nth-child(even) {
      @apply ml-10;
    }
  }
</style>
