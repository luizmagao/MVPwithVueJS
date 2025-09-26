<script setup>
import { onMounted, ref } from "vue";
import NavBar from "@/components/NavBar.vue";
import CardNews from "@/components/CardNews.vue";
import axios from "axios";

const episodes = ref([]);

onMounted(async () => {
  try {
    const response = await axios.get("https://rickandmortyapi.com/api/episode");
    episodes.value = response.data.results;
  } catch (error) {}
});
</script>

<template>
  <nav-bar />

  <div class="grid grid-cols-1 md:grid-cols-3 gap-4 p-4">
    <card-news
      :description="episode.name"
      :label="episode.episode"
      v-for="episode in episodes"
      :key="episode.id"
    />
  </div>
</template>
