<template>
  <div id="app" class="container mt-5">
    <Carousel>
      <CarouselSlide>
        <h3 class="carousel__text">Salut les gens</h3>
        <img width="940" height="300" src="./assets/images/01.jpg" alt="" />
      </CarouselSlide>
      <CarouselSlide>
        <h3 class="carousel__text">Salut les gens</h3>
        <img width="940" height="300" src="./assets/images/02.jpg" alt="" />
      </CarouselSlide>
      <CarouselSlide>
        <h3 class="carousel__text">Salut les gens</h3>
        <img width="940" height="300" src="./assets/images/03.jpg" alt="" />
      </CarouselSlide>
    </Carousel>
  </div>
</template>

<script>
import Carousel from "./components/Carousel/Carousel";
import CarouselSlide from "./components/Carousel/CarouselSlide";

export default {
  name: "App",
  components: {
    Carousel,
    CarouselSlide,
  },
};
</script>

<style src="./app.css">
</style>
