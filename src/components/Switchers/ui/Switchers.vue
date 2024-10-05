<script setup lang="ts">
  import { usePoemStore } from "@/shared/stores";
  import SwitchersItem from "./SwitchersItem.vue";
  const poemStore = usePoemStore();

  function toggleCheckbox(checkbox: HTMLInputElement, id: number) {
    const quatrain = document.getElementById(`quatrain-${id}`) as HTMLDivElement;
    checkbox.checked
      ? quatrain.classList.remove("quatrain_hide")
      : quatrain.classList.add("quatrain_hide");
  }
  function disableCheckbox() {
    const allCheckedChecbox = document.querySelectorAll("input[type='checkbox']:checked");
    allCheckedChecbox.forEach((el) => el.removeAttribute("disabled"));
    if (allCheckedChecbox.length === 1) allCheckedChecbox[0].setAttribute("disabled", "");
  }

  function handleClick(id: number, event: Event) {
    const checkbox = event.currentTarget as HTMLInputElement;

    toggleCheckbox(checkbox, id);
    disableCheckbox();
  }
</script>

<template>
  <div class="flex gap-3">
    <SwitchersItem
      v-for="quatrain in poemStore.quatrains"
      @click="handleClick(quatrain.id, $event)"
      checked
    />
  </div>
</template>

<style lang="scss" scoped></style>
