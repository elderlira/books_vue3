<template>
  <div>progresso {{ progress }}</div>
</template>

<script setup>
import { computed } from "vue";
const props = defineProps(["progresso"]);

const progress = computed(() => {
  return props.progresso.filter((b) => b.isRead).length;
});
</script>