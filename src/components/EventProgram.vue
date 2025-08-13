<template>
  <section id="program" class="program reveal">
    <h2>Программа вечера</h2>
    <ul>
      <li>18:00 — Сбор гостей</li>
      <li>19:00 — Торжественный ужин</li>
      <li>20:30 — Живая музыка и танцы</li>
    </ul>
  </section>
</template>

<script setup></script>

<style scoped>
.program {
  text-align: center;
  padding: 4rem 2rem 2rem;
}

@media (max-width: 600px) {
  .program {
    padding: 2rem 1rem;
  }
}

ul {
  list-style: none;
  padding: 0;
}
li {
  margin: 0.5rem 0;
}
</style>
