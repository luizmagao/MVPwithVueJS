<script setup>
import NavBar from "@/components/NavBar.vue";
import CardExample from "@/components/CardExample.vue";

import axios from "axios";
import { onMounted, ref } from "vue";

const episodes = ref([]);

onMounted(async () => {
  const response = await axios.get("https://rickandmortyapi.com/api/episode");
  episodes.value = response.data.results;
});
</script>

<template>
  <nav-bar />
  <div class="grid grid-cols-1 md:grid-cols-3 grap-3 p-5">
    <card-example
      v-for="episode in episodes"
      :key="episode.id"
      :title="episode.name"
      :label="episode.episode"
      :air-date="episode.air_date"
    />
  </div>
</template>
