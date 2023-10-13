<script setup lang="ts">
import TheCategoryNav from "@/components/TheCategoryNav.vue";
import TheCategoryBookList from "@/components/TheCategoryBookList.vue";
import {useRoute} from "vue-router";
import {useBookStore} from "@/stores/book";
import {watch} from "vue";

const route = useRoute();

const bookStore = useBookStore();

watch(
  () => route.params.name,
  async (newName) => {
    await bookStore.fetchBooks(newName as string);
  },
  { immediate: true }
);
</script>

<style scoped>

.category-page {
  background-color: var(--background-tan-color);
}

</style>

<template>
 <div class="category-page">
  <the-category-nav></the-category-nav>
  <the-category-book-list></the-category-book-list>
 </div>
</template>