<template>
    <div class="carousel">
      <div class="carousel-inner" :style="{ transform: `translateX(-${currentSlide * 100}%)` }">
        <div class="carousel-item" v-for="(slide, index) in slides" :key="index">
          <img :src="slide.image" :alt="slide.alt" style="width: 50%; height: auto;">
        </div>
      </div>
      <button class="carousel-control-prev" @click="prevSlide">‹</button>
      <button class="carousel-control-next" @click="nextSlide">›</button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'CarrouselComponent',
    props: {
      slides: {
        type: Array,
        required: true
      }
    },
    data() {
      return {
        currentSlide: 0
      };
    },
    methods: {
      nextSlide() {
        this.currentSlide = (this.currentSlide + 1) % this.slides.length;
      },
      prevSlide() {
        this.currentSlide = (this.currentSlide - 1 + this.slides.length) % this.slides.length;
      }
    }
  };
  </script>
  
  <style scoped>
  .carousel {
    position: relative;
    width: 100%;
    overflow: hidden;
  }
  .carousel-inner {
    display: flex;
    transition: transform 0.5s ease;
  }
  .carousel-item {
    min-width: 100%;
    box-sizing: border-box;
  }
  .carousel-control-prev,
  .carousel-control-next {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background-color: rgba(0, 0, 0, 0.5);
    border: none;
    color: white;
    padding: 10px;
    cursor: pointer;
  }
  .carousel-control-prev {
    left: 10px;
  }
  .carousel-control-next {
    right: 10px;
  }
  </style>