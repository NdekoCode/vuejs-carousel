<template>
  <div id="app" class="container mt-5">
    <Carousel>
      <CarouselSlide v-for="slide in nbrSlides" :key="slide" :index="slide - 1">
        <h3 class="carousel__text">Salut les gens {{ slide }}</h3>
        <img
          width="940"
          height="300"
          :src="
            require('@/assets/images/' +
              slide.toString().padStart(2, '0') +
              '.jpg')
          "
          alt=""
        />
      </CarouselSlide>
    </Carousel>
    <div><button @click="addSlide">Ajouter un slide</button></div>
  </div>
</template>

<script>
import Carousel from "./components/Carousel/Carousel";
import CarouselSlide from "./components/Carousel/CarouselSlide";

export default {
  name: "App",
  data() {
    return {
      nbrSlides: 5,
    };
  },
  methods: {
    addSlide() {
      if (this.nbrSlides < 10) {
        this.nbrSlides += 1;
      } else {
        this.nbrSlides = 10;
      }
    },
  },
  components: {
    Carousel,
    CarouselSlide,
  },
};
</script>

<style src="./app.css">
</style>
