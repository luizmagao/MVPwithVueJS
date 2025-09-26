<script setup>
import { ref, watch, watchEffect } from "vue";
import NavBar from "@/components/NavBar.vue";

const first_name = ref("Luiz");

watch(first_name, (newValue, oldValue) => {
  console.log(oldValue);
  console.log(newValue);
});

const todo = ref(1);
const data = ref(null);

watchEffect(async () => {
  const response = await fetch(`https://jsonplaceholder.typicode.com/todos/${todo.value}`);
  data.value = await response.json();
});
</script>

<template>
  <nav-bar />

  <input type="text" placeholder="neutral" class="input input-neutral" v-model="todo" />
  <pre>
    {{ data }}
  </pre>
</template>
