<template>
  <div class="card bg-base-100 w-96 shadow-sm">
    <avatar-images />
    <div class="card-body">
      <h2 class="card-title">
        {{ description }}
        <div class="badge badge-secondary">{{ label }}</div>
      </h2>
      <p>
        A card component has a figure, a body part, and inside body there are title and actions
        parts
      </p>
      <div class="card-actions justify-end">
        <div class="badge badge-outline">Fashion</div>
        <div class="badge badge-outline">Products</div>
      </div>
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
