<template>
  <div class="parallax-section" ref="section">
    <div
      class="parallax-bg"
      :style="{
        backgroundImage: `url(${image})`,
        transform: `translateX(${offset}px)`,
      }"
    ></div>
    <div class="content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    speed: Number,
    image: String,
  },
  data() {
    return {
      offset: 0,
      observer: null,
    }
  },
  mounted() {
    this.observer = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          window.addEventListener('scroll', this.handleScroll)
        } else {
          window.removeEventListener('scroll', this.handleScroll)
        }
      })
    })

    this.observer.observe(this.$refs.section)
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll)
    if (this.observer) this.observer.disconnect()
  },
  methods: {
    handleScroll() {
      const rect = this.$refs.section.getBoundingClientRect()
      this.offset = (window.scrollY - rect.top) * this.speed
    },
  },
}
</script>

<style>
.parallax-section {
  position: relative;
  height: 100vh;
  overflow: hidden;
}

.parallax-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  will-change: transform;
}

.content {
  position: relative;
  z-index: 2;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
}
</style>
