<template>
  <section class="hero reveal">
    <h1>Приглашение на 60-летие</h1>
    <p>Дорогие друзья! Приглашаем вас на торжественное празднование юбилея.</p>
  </section>
</template>

<script setup></script>

<style scoped>
.hero {
  text-align: center;
  padding: 4rem 2rem 2rem;
}

@media (max-width: 600px) {
  .hero {
    padding: 2rem 1rem;
  }

  .hero h1 {
    font-size: 1.8rem;
  }
}
</style>
