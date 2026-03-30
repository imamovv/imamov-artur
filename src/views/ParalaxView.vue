<template>
  <div class="parallax-scene">
    <ParallaxSection
      v-for="(section, index) in sections"
      :key="index"
      :speed="section.speed"
      :image="section.image"
    />
  </div>
</template>

<script>
import ParallaxSection from '../components/ParallaxSection.vue'

export default {
  components: { ParallaxSection },
  data() {
    return {
      sections: [
        { speed: 0.2, image: 'src/assets/images/1.jpg' },
        { speed: 0.3, image: 'src/assets/images/2.jpg' },
        { speed: 0.2, image: 'src/assets/images/3.jpg' },
      ],
    }
  },
}
</script>
