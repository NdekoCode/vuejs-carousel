<template>
  <transition name="slide">
    <div v-if="visible">
      <slot></slot>
    </div>
  </transition>
</template>
<script>
export default {
  name: "CarouselSlide",
  data() {
    return {
      index: 0,
    };
  },
  computed: {
    visible() {
      // Si l'index de ce slide est egale à l'index courrant du carrouse donc cet element est visible
      return this.index === this.$parent.index;
    },
  },
};
</script>
<style scoped>
.slide-enter-active {
  animation: slideIn 0.35s;
}
@keyframes slideIn {
  from {
    transform: translateX(100%);
  }
  to {
    transform: translateX(0);
  }
}
</style>