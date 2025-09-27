<template>
  <div class="avatar-group -space-x-6 mt-5 ml-5">
    <div class="avatar" v-for="character in charactersShow()" :key="character.id">
      <div class="w-12">
        <img src="https://img.daisyui.com/images/profile/demo/batperson@192.webp" />
      </div>
    </div>
    <div class="avatar avatar-placeholder">
      <div class="bg-neutral text-neutral-content w-12">
        <span>{{ qntCharacters(characters) }}</span>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  characters: Array,
});

function qntCharacters(characters) {
  if (characters.length < 4) {
    return characters.length;
  }
  return characters.length - 4;
}

const charactersShow = () => {
  return props.characters.splice(0, 4);
};

console.log(charactersShow());
</script>

<style lang="scss" scoped></style>
