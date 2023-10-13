CategoryBookListItem - Good w/ Add to Cart Not at bottom

<script setup lang="ts">
import { defineProps } from "vue";
import type { BookItem } from "@/types";

import { useCartStore } from "@/stores/cart";
const cartStore = useCartStore();

const props = defineProps<{
  book: BookItem;
}>();
const bookImagePrefix = `${import.meta.env.BASE_URL}/book-images`;
const bookImageFileName = function (book: BookItem): string {
  let name = book.title.toLowerCase();
  name = name.replace(/ /g, "-");
  name = name.replace(/'/g, "");
  return `${name}.gif`;
};

</script>
<style scoped>

.book-box {
  position: relative;
  display: flex;
  flex-direction: column;
  background-color: var(--secondary-background-color);
  padding: 0.5em;
  gap: 0.25em;
  margin: 15px;
  text-align: center; /* Center the content horizontally */
  justify-content: space-between; /* Distribute items evenly along the main axis */
  min-width: 130px;
  width: 190px;
  height: 386px;
}

.book-image {
  display: inline-block;
  height: 200px;
  width: auto;
  max-width: 100%;
  position: relative;
}

.book-image img {
  height: 200px;
  width: auto;
  display: block;
}

.book-title {
  padding-top: 4px;
  font-size: 19px;
  font-weight: bold;
  padding-bottom: 5px;
}

.book-author {
  font-size: 18px;
}

.book-price {
  font-size: 17px;
  font-weight: bold;
  margin-bottom: 5px;
}

.read-now-button {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 14px;
  white-space: nowrap;
  padding: 5px 10px;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  background-color: var(--call-to-action-button-color);
}

.add-to-cart-button {
  box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
  border-width: 0;
  display: block;
  width: 100%;
  border-radius: 15px;
  background-color: var(--category-button-color);
  color: white;
  padding: 5px;
  font-size: 20px;
}

.book-title-link {
  text-decoration: none;
  color: black;
}

.book-author-link {
  text-decoration: none;
  color: black;
}

.book-price-link {
  text-decoration: none;
  color: black;
}

.book-details {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  flex-grow: 1;
}

.book-image-link {
  display: inline-block;
}

</style>

<template>
  <li class="book-box">
    <div class="book-image">
      <router-link class="book-image-link" to="">
        <img
            :src="`${bookImagePrefix}/${bookImageFileName(book)}`"
            :alt="book.title"
            class="book"
        />
      </router-link>
      <button v-if="book.isPublic" class="button read-now-button">Read Now</button>
    </div>
      <router-link to="" class="book-title-link">
      <div class="book-title">{{ book.title }}</div>
      </router-link>
      <router-link to="" class="book-author-link">
        <div class="book-author">{{ book.author }}</div>
      </router-link>
      <router-link to="" class="book-price-link">
        <div class="book-price">${{ (book.price / 100).toFixed(2) }}</div>
      </router-link>
      <button @click="cartStore.addToCart(book)" class="button add-to-cart-button">Add to Cart</button>
  </li>
</template>
