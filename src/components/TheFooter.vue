<script setup lang="ts">
</script>

<style scoped>
footer {
  background: var(--secondary-background-color);
  justify-content: space-between; /* Distribute items evenly along the main axis */
  display: flex;
  gap: 1em;
}

.copyright {
  display: flex;
  flex-direction: row;
  color: white;
  font-size: 24px;
  margin-top: auto;
  margin-bottom: auto;
}

#copyright-symbol {
  padding-top: 5px;
  margin-right: 10px;
}

.links a {
  margin-left: 10px;
  font-size: 30px;
  text-decoration: none;
  color: white;
}

.links a:hover {
  color: var(--footer-links-color);
}

.links {
  display: flex;
  flex-direction: row;
  margin-top: auto;
  margin-bottom: auto;
  color: white;
}

.page-link {
  margin-right: 10px;
  font-size: 22px;
}

.social-media-icons {
  display: flex;
  flex-direction: row;
  margin-right: 18px;
  font-size: 36px;
  color: white;
}

.social-media-icons a {
  margin-top: auto;
  margin-bottom: auto;
  color: white;
  text-decoration: none;
}

.social-media-icons a:hover {
  color: var(--footer-links-color);
  text-decoration: none;
}

.social-media-icons {
  text-align: center;
  gap: 0.25em;
}

</style>

<template>
  <footer class="container">
    <section class="copyright">
      <i id="copyright-symbol" class="fa-regular fa-copyright"></i>
      <p>2023 Brown Bear Books</p>
    </section>

    <section class="links">
      <router-link to="/" class="page-link">About</router-link>
      <router-link to="/" class="page-link">Contact</router-link>
      <router-link to="/" class="page-link">Directions</router-link>
    </section>
    <section class="social-media-icons">
      <router-link to="/"><i class="fa-brands fa-instagram"></i></router-link>
      <router-link to="/"><i class="fa-brands fa-twitter"></i></router-link>
      <router-link to="/"><i class="fa-brands fa-facebook"></i></router-link>
    </section>
  </footer>
</template>
