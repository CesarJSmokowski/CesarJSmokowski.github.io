<script setup lang="ts">
import { apiUrl } from "@/api";
import type { CategoryItem } from "@/types";

import { useCategoryStore } from "@/stores/category";
const categoryStore = useCategoryStore();

</script>

<style scoped>
.header-dropdown {
  position: relative;
}

.categories-button {
  margin-top: 0.25em;
  background-color: var(--category-button-color);
  border: 0;
  border-radius: 15px;
  padding: 6px;
  color: white;
  font-size: 26px;
}

.category-list {
  border-radius: 15px;
  width: 160px;
  font-size: 22px;
}

.header-dropdown ul {
  display: none;
  background-color: white;
  color: black;
}

.header-dropdown li {
  padding: 0.25em 0.5em;
}

.header-dropdown a {
  color: black;
  text-decoration: none;
}

.header-dropdown li:hover {
  background: lightgray;
}

.header-dropdown:hover ul {
  position: absolute;
  z-index: 1;
  display: block;
  min-width: 160px;
  cursor: pointer;
}
</style>

<template>
  <div class="header-dropdown">
    <button class="button categories-button">
      Categories
      <i class="fa-solid fa-sort-down"></i>
    </button>
    <ul class="category-list">
      <router-link
          v-for="category in categoryStore.categoryList"
          :key="category.categoryId"
          :to="'/category/' + category.name"
          class="category-link"
      >
        <li class="category-list">{{ category.name }}</li>
      </router-link>
    </ul>
  </div>
</template>
