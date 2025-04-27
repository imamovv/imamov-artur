<template>
  <header class="navbar">
    <nav>
      <a href="#program">Программа</a>
      <a href="#location">Место</a>
      <a href="#gallery">Фото</a>
      <a href="#rsvp">Ответить</a>
    </nav>
  </header>

  <main class="content">
    <HeroSection />
    <EventProgram />
    <LocationDetails />
    <PhotoGallery />
    <RSVPForm />
  </main>
</template>

<script setup>
import HeroSection from './HeroSection.vue'
import EventProgram from './EventProgram.vue'
import LocationDetails from './LocationDetails.vue'
import PhotoGallery from './PhotoGallery.vue'
import RSVPForm from './RSVPForm.vue'
</script>

<style scoped>
.navbar {
  position: fixed; /* фиксируем наверху */
  width: 100%;
  top: 0;
  left: 0;
  background: #1a1f36;
  padding: 1rem 0;
  z-index: 10;
}

.navbar nav {
  display: flex;
  justify-content: center;
  gap: 0.4rem;
}

.navbar a {
  color: #d4af37;
  text-decoration: none;
  font-weight: bold;
  font-size: 1.1rem;
  transition: color 0.3s;
}

.navbar a:hover {
  color: #ffffff;
}

/* добавляем отступ для всего контента, чтобы не залез под navbar */
.content {
  padding-top: 80px;
}
</style>
