<script setup lang="ts">
  import Switchers from "@/components/Switchers";
  import { usePoemStore } from "@/shared/stores";

  const poemStore = usePoemStore();
</script>

<template>
  <div class="mt-10 flex justify-center">
    <div class="relative flex w-[400px] flex-col gap-5 md:gap-10">
      <Switchers class="justify-center md:absolute md:-left-[50%] md:top-0 md:justify-start" />
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
