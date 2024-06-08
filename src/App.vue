<template>
  <div id="app">
    <CarrouselComponent :slides="slides" />
    
  </div>
</template>

<script>
import CarrouselComponent from './components/CarrouselComponent.vue';

export default {
  name: 'App',
  components: {
    CarrouselComponent
  },
  data() {
    return {
      slides: [
        { image: '1300753.jpg', alt: 'Slide 1' },
        { image: '1301850.jpg', alt: 'Slide 2' },
        { image: '1305880.jpeg', alt: 'Slide 3' },
        { image: '1308320.jpeg', alt: 'Slide 4' }
      ]
    };
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  margin-top: 60px;
}
</style>