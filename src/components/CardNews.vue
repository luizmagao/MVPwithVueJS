<template>
  <div class="card bg-base-100 w-96 shadow-sm">
    <avatar-images />
    <div class="card-body">
      <h2 class="card-title">
        {{ description }}
        <div class="badge badge-secondary">{{ label }}</div>
      </h2>
    </div>
  </div>
</template>

<script setup>
import AvatarImages from "./AvatarImages.vue";
defineProps({
  description: String,
  label: String,
});
</script>

<style lang="scss" scoped></style>
