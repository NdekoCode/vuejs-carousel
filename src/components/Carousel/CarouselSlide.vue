<template>
  <div v-if="visible">
    Index: {{ index }} Visible ? {{ visible }}
    <slot></slot>
  </div>
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
<style></style>