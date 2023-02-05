<template>
  <div id="app" class="container">
    <Carousel>
      <CarouselSlide>Salut les gens</CarouselSlide>
      <CarouselSlide>Salut les geeks</CarouselSlide>
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
