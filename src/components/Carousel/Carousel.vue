<template>
  <div>
    <div class="carousel">
      <CarouselSlide v-for="slide in nbrSlides" :index="slide - 1" :key="slide">
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
      <button class="carousel__nav carousel__prev" @click.prevent="prev">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="ionicon"
          heigth="24"
          width="24"
          viewBox="0 0 512 512"
        >
          <title>Chevron Back</title>
          <path
            fill="none"
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="48"
            d="M328 112L184 256l144 144"
          />
        </svg>
      </button>
      <button class="carousel__nav carousel__next" @click.prevent="next">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="ionicon"
          heigth="24"
          width="24"
          viewBox="0 0 512 512"
        >
          <title>Chevron Forward</title>
          <path
            fill="none"
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="48"
            d="M184 112l144 144-144 144"
          />
        </svg>
      </button>
      <div class="carousel__pagination">
        <button
          class=""
          v-for="item in slidesCount"
          :key="item"
          @click="goTo(item - 1)"
          :class="{ active: item - 1 === index }"
        ></button>
      </div>
    </div>
    <!-- <div class="carousel">
      <button class="btn" @click.stop="addSlide">Ajouter un slide</button>
      <button class="btn" @click.stop="removeSlide">Supprimer un slide</button>
    </div> -->
  </div>
</template>

<script>
import CarouselSlide from "./CarouselSlide";
export default {
  name: "Carousel",
  data() {
    return {
      index: 0,
      slides: [],
      direction: "right",
      nbrSlides: 5,
    };
  },
  methods: {
    goTo(index) {
      this.direction = index > this.index ? "right" : "left";
      this.index = index;
    },
    next() {
      this.direction = "right";
      if (this.index < this.slidesCount - 1) {
        this.index++;
      } else {
        this.index = 0;
      }
    },
    prev() {
      this.direction = "left";
      if (this.index > 0) {
        this.index--;
      } else {
        this.index = this.slidesCount - 1;
      }
    },
    addSlide() {
      if (this.nbrSlides < 10) {
        this.nbrSlides++;
      }
    },
    /*  removeSlide() {
      if (this.nbrSlides >= 1 && this.nbrSlides !== this.index + 1) {
        this.nbrSlides -= 1;
      }
      this.$forceUpdate();
    }, */
  },
  computed: {
    slidesCount() {
      return this.slides.length;
    },
  },
  components: {
    CarouselSlide,
  },
  mounted() {
    this.slides = this.$children;
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.carousel {
  position: relative;
}
.carousel__nav {
  height: 65px;
  background-color: #222;
  color: #eee;
  width: 65px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: absolute;
  left: 15px;
  top: 50%;
  transform: translateY(-50%);
  cursor: pointer;
}
.carousel__nav.carousel__next {
  right: 15px;
  left: auto;
  transform: translateY(-50%);
}
.carousel__nav svg {
  fill: currentColor;
}
</style>
