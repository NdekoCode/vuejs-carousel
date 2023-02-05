<template>
  <div id="app" class="container mt-5">
    <Carousel />
  </div>
</template>

<script>
import Carousel from "./components/Carousel/Carousel";

export default {
  name: "App",
  components: {
    Carousel,
  },
};
</script>

<style src="./app.css">
</style>
