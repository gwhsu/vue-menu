<template>
  <Carousel :itemsToShow="3.95" :wrapAround="true" :transition="500">
    <Slide v-for="imageIndex in 3" :key="imageIndex">
      <div class="carousel__item">
        <img :src="`/images/${imageIndex}.jpg`" alt="slide image" class="menu-image">
      </div>
    </Slide>
  </Carousel>
</template>

<script>
import { defineComponent } from 'vue'
import { Carousel, Slide } from 'vue3-carousel'

import 'vue3-carousel/dist/carousel.css'

export default defineComponent({
  name: 'Autoplay',
  components: {
    Carousel,
    Slide,
  },
})
</script>

<style scoped>
.carousel__item {
  padding: 5px;
}

.menu-image {
  max-width: 100%;  
  max-height: 100%; 
  object-fit: contain; 
}

.carousel__viewport {
  perspective: 2000px;
}

.carousel__track {
  transform-style: preserve-3d;
}

.carousel__slide--sliding {
  transition: 0.5s;
}

.carousel__slide {
  opacity: 0.9;
  transform: rotateY(-20deg) scale(0.9);
}

.carousel__slide--active ~ .carousel__slide {
  transform: rotateY(20deg) scale(0.9);
}

.carousel__slide--prev {
  opacity: 1;
  transform: rotateY(-10deg) scale(0.95);
}

.carousel__slide--next {
  opacity: 1;
  transform: rotateY(10deg) scale(0.95);
}

.carousel__slide--active {
  opacity: 1;
  transform: rotateY(0) scale(1.1);
}
</style>
