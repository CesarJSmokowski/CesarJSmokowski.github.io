<script setup lang="ts">
const bookImagePrefix = `${import.meta.env.BASE_URL}/book-images`;

// Import useRouter from Vue Router
import { useRouter } from "vue-router";

// Define the function to navigate to the "/category/Classics" page
const navigateToClassics = () => {
  console.log("navigateToClassics Called");
  const router = useRouter();
  router.push("/category/Classics");
};

</script>

<style scoped>
.home-page {
  display: flex;
  background-color: var(--background-tan-color);
  flex-direction: column;
  justify-content: space-between; /* Distribute items evenly along the main axis */
}

.call-to-action-button {
  margin-top: 25px;
  margin-left: auto;
  margin-right: auto;
}

.call-to-action-button button {
  padding: 15px;
  font-size: 30px;
  font-weight: 550;
  border-radius: 10px;
  background-color: var(--call-to-action-button-color);
}

.mystery-picks-section {
  font-size: 26px;
  margin-top: 20px;
  margin-left: auto;
  margin-right: auto;
  display: flex;
  flex-direction: row;
}

.staff-picks-title-section {
  font-size: 34px;
  font-weight: bold;
  margin-top: 25px;
  margin-bottom: 15px;
  margin-left: auto;
  margin-right: auto;
}

.mystery-picks-section a {
  font-weight: bold;
  color: var(--footer-links-color);
  text-decoration: none;
}

.button-categories-button:hover,
.button-categories-button:active {
  background: var(--primary-color-dark);
  color: white;
}

.button-categories-button {
  border-width: 0;
  box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
}

.welcome-text {
  width: 20em;
}

.category-box-list {
  display: flex;
  flex-direction: row;
  margin-right: 20px;
  margin-left: 20px;
  margin-bottom: 25px;
  justify-content: space-between; /* Distribute items evenly along the main axis */
  text-decoration: none;
}

.category-link {
  text-decoration: none;
  color: black;
}

.category-image {
  height: 200px;
  width: auto;
  margin-bottom: 15px;
}

.category-box {
  text-align: center;
}

.grow-on-hover {
  transition: transform 0.3s ease; /* Add a smooth transition effect */
}

/* Define the hover effect for the button */
.grow-on-hover:hover {
  transform: scale(1.35); /* Increase the size of the button on hover */
}

.category-name {
  font-size: 28px;
}

</style>
<template>
  <div class="home-page">
    <section class="call-to-action-button">
      <router-link 
        :key="1001" 
        :to="'/category/Classics'"
        class="call-to-action-link"
      >
        <button class="button button-categories-button grow-on-hover">
          Shop Must Reads
        </button>
      </router-link>
    </section>
    <section class="mystery-picks-section">
      <p>Find new favorites with <router-link to="/">mystery picks <i class="fa-solid fa-dice"></i></router-link></p>
    </section>
    <section class="staff-picks-title-section">
      <p>Explore Popular Genres</p>
    </section>

    <section class="category-box-list">
      <section class="category-box">
        <router-link
        :to="'/category/Classics'"
        class="category-link"
        >
        <img
            src="/site-images/ClassicsGenre2.jpeg"
            :alt="'Classics Genre'"
            class="category-image"
        />
          <h1 class="category-name">Classics</h1>
        </router-link>
      </section>
      <section class="category-box">
        <router-link
        :to="'/category/Fantasy'"
        class="category-link"
        >
        <img
            src="/site-images/FantasyGenre2.jpeg"
            :alt="'Fantsy Genre'"
            class="category-image"
        />
          <h1 class="category-name">Fantasy</h1>
        </router-link>
      </section>
      <section class="category-box">
        <router-link
        :to="'/category/Mystery'"
        class="category-link"
        >
        <img
            src="/site-images/MysteryGenre.jpeg"
            :alt="'Mystery Genre'"
            class="category-image"
        />
          <h1 class="category-name">Mystery</h1>
        </router-link>
      </section>
      <section class="category-box">
        <router-link
        :to="'/category/Romance'"
        class="category-link"
        >
        <img
            src="/site-images/RomanceGenre2.jpeg"
            :alt="'Romance Genre'"
            class="category-image"
        />
          <h1 class="category-name">Romance</h1>
        </router-link>
      </section>
    </section>
  </div>
</template>
