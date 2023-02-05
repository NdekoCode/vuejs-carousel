<template>
  <transition :name="transition">
    <div v-if="visible">
      <slot></slot>
    </div>
  </transition>
</template>
<script>
export default {
  name: "CarouselSlide",
  props: {
    index: { type: Number, default: 0 },
  },
  computed: {
    transition() {
      if (this.$parent.direction) {
        return (
          "slide" +
          this.$parent.direction[0].toUpperCase() +
          this.$parent.direction.substr(1, this.$parent.direction.length)
        );
      }
      return null;
    },
    visible() {
      // Si l'index de ce slide est egale à l'index courrant du carrouse donc cet element est visible
      return this.index === this.$parent.index;
    },
  },
};
</script>
<style scoped>
.slideRight-enter-active {
  animation: slideRightIn 0.35s;
}
.slideLeft-enter-active {
  animation: slideRightOut 0.35s reverse;
}
.slideLeft-leave-active {
  animation: slideRightIn 0.35s reverse;
  position: absolute;
  inset: 0;
  width: 100%;
}
.slideRight-leave-active {
  animation: slideRightOut 0.35s;
  position: absolute;
  inset: 0;
  width: 100%;
}
@keyframes slideRightIn {
  from {
    transform: translateX(100%);
  }
  to {
    transform: translateX(0);
  }
}

@keyframes slideRightOut {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-100%);
  }
}
</style>