<template>
  <div class="books-list">
    <div class="book" v-for="(b, index) in books" :key="index">
      <div class="book-cover">
        <img :src="b.cover" />

        <button :class="{ isRead: b.isRead }" @click="$emit('lido', b.id)">
          <i class="fa-solid fa-eye"></i>
          <span>{{ b.isRead ? "Já li" : "Não li" }}</span>
        </button>
      </div>

      <div class="book-details">
        <p class="book-author">{{ b.author }}</p>
        <h3 class="book-title">{{ b.title }}</h3>
        <p><i class="fa-solid fa-hashtag icon"></i> {{ b.isbn }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(["books"]);
</script>
