<template>
  <div class="userProgress">
    <div>progresso do usuário</div>
    <progress :value="booksRead" :max="progresso.length" />
    <p>{{ booksFinished }}</p>
    {{ show }}
  </div>
</template>

<script setup>
import { computed } from "vue";
const props = defineProps(["progresso", "show"]);

const booksRead = computed(() => {
  return props.progresso.filter((b) => b.isRead).length;
});

const booksFinished = computed(() => {
  return booksRead.value >= props.progresso.length
    ? "Parabens, você leu todos os livros"
    : `${booksRead.value} de ${props.progresso.length}`;
});
</script>

<style>
.userProgress {
  margin-top: 50px;
  text-align: center;
}
</style>