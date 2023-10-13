<script setup lang="ts">
import TheHeaderDropdown from "@/components/TheHeaderDropdown.vue";
import { useCartStore } from "@/stores/cart";
const cartStore = useCartStore();
</script>

<style scoped>
header {
  display: flex;
  flex-direction: row;
  padding: 1em;
  background: var(--secondary-background-color);

  gap: 1em;
}

.title {
  margin: auto;
}

.title-text-link {
  text-decoration: none;
  color: inherit;
}

.title-text {
  color: #5E1604;
  font-size: 30px;
}

.bookstore-logo {
  display: flex;
  margin-top: auto;
  margin-bottom: auto;
}

.search-bar-and-magnifying-glass {
  margin: auto;
  display: flex;
  flex-direction: row;
}

.search-bar {
  margin-right: 15px;
  border-radius: 15px;
  width: 300px;
}

.search-bar-and-button-section {
  margin: auto;
  display: flex;
  flex-direction: row;
}

.search-bar-and-button-form {
  display: flex;
  flex-direction: row;
  border-width: 0;
}

.category-button-section {
  margin: auto;
}

.category-dropdown-item {
  font-size: 24px;
}

.header-dropdown {
  float:left;
  position: relative;
  display: inline-block;
}

.cart-and-profile {
  position: relative;
}

.search-bar-and-icon {
  position: relative;
  display: inline-block;
}

#search-bar-icon {
  position: absolute;
  top: 30%;
  right: 5%;
  color: black;
  font-weight: bold;
  padding: 0px 12px;
  font-size: 22px;
}

.category-list {
  border-radius: 15px;
  width: 160px;
}

.icon-container {
  position: relative;
  display: inline-block;
}

.cart-icon {
  font-size: 48px;
  color: black;
  padding-top: 8px;
  margin-right: 20px;
}

.badge {
  position: absolute;
  top: 8%;
  right: 45%;
  color: white;
  font-size: 24px;
}

.sign-in-container {
  display: flex;
  flex-direction: row;
}

.sign-in-icon-link {
  text-decoration: none;
  color: black;
}

.sign-in-name-link {
  text-decoration: none;
  color: black;
}

#user-icon {
  margin-right: 10px;
  margin-top: 10px;
  font-size: 48px;
}

.user-name {
  padding-top: 10px;
  font-size: 32px;
}

header {
  background: var(--secondary-background-color);
  display: flex;
  justify-content: space-between; /* Distribute items evenly along the main axis */
  padding: 1em;
  gap: 1em;
}

.search-bar {
  margin-top: 0.25em;
  margin-right: 15px;
  border-radius: 15px;
  height: 43px;
  border-width: 0;
}

.cart-and-sign-in {
  display: flex;
  flex-direction: row;
  margin-top: auto;
  margin-bottom: auto;
}



@media (max-width: 600px) {
  header {
    flex-direction: column;
  }
}
</style>

<template>
  <header class="container">
    <section class="bookstore-logo">
      <section style="width: 100px; float:left; height:100px; margin:10px">
        <router-link to="/">
          <img
              src="/site-images/BrownBearBooksLogo.png"
              alt="Brown Bear Books"
              width="125"
              height="auto"
          />
        </router-link>
      </section>
      <section class="title">
        <router-link to="/" class="title-text-link">
          <h1 class="title-text">Brown <br>Bear <br>Books</h1>
        </router-link>
      </section>
    </section>

    <section class="search-bar-and-magnifying-glass">
      <div class="search-bar-and-icon">
        <form action="category.html" class="search-bar-and-button-form">
          <input type="text" class="search-bar"/>
        </form>
        <i id="search-bar-icon" class="fa-solid fa-magnifying-glass"></i>
      </div>
      <the-header-dropdown></the-header-dropdown>
    </section>

    <section class="cart-and-sign-in">
      <div class="icon-container">
        <router-link to="/">
          <i id="cart-logo" class="cart-icon fas fa-shopping-cart"></i>
          <p class="badge">{{ cartStore.count }}</p>
        </router-link>
      </div>
      <div class="sign-in-container">
        <router-link to="/" class="sign-in-icon-link">
          <i id="user-icon" class="fa-solid fa-circle-user"></i>
        </router-link>
        <router-link to="/" class="sign-in-name-link">
          <p class="user-name">Cesar</p>
        </router-link>
      </div>
    </section>
  </header>
</template>
