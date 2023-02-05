<template>
  <div>
    <slot></slot>
    <button class="carousel__nav carousel__next" @click.prevent="next">
      Suivant
    </button>
    <button class="carousel__nav carousel__prev" @click.prevent="prev">
      Precedent
    </button>
  </div>
</template>

<script>
export default {
  name: "Carousel",
  data() {
    return {
      index: 0,
      slides: [],
    };
  },
  methods: {
    next() {
      if (this.index < this.slidesCount - 1) {
        this.index++;
      } else {
        this.index = 0;
      }
    },
    prev() {
      if (this.index > 0) {
        this.index--;
      } else {
        this.index = this.slidesCount - 1;
      }
    },
  },
  computed: {
    slidesCount() {
      return this.slides.length;
    },
  },
  mounted() {
    this.slides = this.$children;
    this.slides.forEach((slide, index) => {
      slide.index = index;
    });
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.carousel {
  position: relative;
}
</style>
