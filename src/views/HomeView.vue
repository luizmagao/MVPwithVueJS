<script setup>
import { ref, watch, watchEffect } from "vue";

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
  <div class="navbar bg-base-100 shadow-sm">
    <div class="flex-1">
      <a class="btn btn-ghost text-xl">daisyUI</a>
    </div>
    <div class="flex-none">
      <ul class="menu menu-horizontal px-1">
        <li><a>Link</a></li>
        <li>
          <details>
            <summary>Parent</summary>
            <ul class="bg-base-100 rounded-t-none p-2">
              <li><a>Link 1</a></li>
              <li><a>Link 2</a></li>
            </ul>
          </details>
        </li>
      </ul>
    </div>
  </div>
  <input type="text" placeholder="neutral" class="input input-neutral" v-model="todo" />
  <pre>
    {{ data }}
  </pre>
</template>
