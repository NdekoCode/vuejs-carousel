<template>
  <div id="app" class="container">
    <Carousel>
      <CarouselSlide>
        <p>Salut les gens</p>
        <img src="https://loremflickr.com/630/300/mangas?lock=1" alt="" />
      </CarouselSlide>
      <CarouselSlide
        ><p>Salut les geeks</p>

        <img
          src="https://loremflickr.com/630/300/jujutsukaisen?lock=2"
          alt=""
        />
      </CarouselSlide>
      <CarouselSlide>
        <p>Salut les geeks</p>

        <img src="https://loremflickr.com/630/300/mangas?lock=3" alt="" />
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
