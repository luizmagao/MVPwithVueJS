<script setup>
import NavBar from "@/components/NavBar.vue";
import CardExample from "@/components/CardExample.vue";
</script>

<template>
  <nav-bar />
  <div class="grid grid-cols-1 md:grid-cols-3 grap-3 p-5">
    <card-example />
    <card-example />
    <card-example />
  </div>
</template>
