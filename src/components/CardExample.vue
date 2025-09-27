<template>
  <div class="card bg-base-100 w-96 shadow-sm my-4">
    <avatar-persons :characters="characters" />
    <div class="card-body">
      <h2 class="card-title">
        {{ title || "Aguardando dados" }}
        <div class="badge badge-secondary">{{ label }}</div>
      </h2>
      <div class="card-actions justify-end">
        <div class="badge badge-outline">{{ airDate || "- - -" }}</div>
      </div>
    </div>
  </div>
</template>

<script setup>
import AvatarPersons from "./AvatarPerson.vue";
defineProps({
  title: String,
  label: String,
  airDate: String,
  characters: Array,
});
</script>

<style lang="scss" scoped></style>
