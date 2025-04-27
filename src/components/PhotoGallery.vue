<template>
  <section id="gallery" class="gallery">
    <h2>Фотогалерея</h2>
    <div class="photos">
      <img v-for="(photo, index) in photos" :key="index" :src="photo" alt="Фото" />
    </div>
  </section>
</template>

<script setup>
import image1 from '@/assets/images/1.jpg'
import image2 from '@/assets/images/2.jpg'
import image3 from '@/assets/images/3.jpg'
const photos = [image1, image2, image3]
</script>

<style scoped>
.gallery {
  text-align: center;
}

.photos {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  justify-content: center;
  margin-top: 2rem;
}

.photos img {
  width: 300px;
  height: 200px;
  object-fit: cover;
  border-radius: 12px;
  transition: transform 0.3s ease;
}

.photos img:hover {
  transform: scale(1.05);
}
</style>
