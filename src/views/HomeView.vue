<script setup>
import NavBar from "@/components/NavBar.vue";
import CardNews from "@/components/CardNews.vue";
</script>

<template>
  <nav-bar />

  <div class="grid grid-cols-1 md:grid-cols-3 gap-4 p-4">
    <card-news />
    <card-news />
    <card-news />
    <card-news />
  </div>
</template>
