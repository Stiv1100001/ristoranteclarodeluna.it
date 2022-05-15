<script>
export default {
  name: 'Carousel',
  data: () => ({
    currentIndex: 0,
    slider: null,
  }),
  props: {
    slides: {
      type: Array,
      required: true,
    },
  },
  methods: {
    slide(direction) {
      if (direction === 'next') {
        this.currentIndex++;
        if (this.currentIndex >= this.slides.length) this.currentIndex = 0;
      } else if (direction === 'prev') {
        this.currentIndex--;
        if (this.currentIndex < 0) this.currentIndex = this.slides.length - 1;
      }
    },
    manualSlide(direction) {
      clearInterval(this.slider);
      this.slider = null;
      this.slide(direction);
    },
  },
  mounted() {
    this.slider = setInterval(this.slide, 2000, 'next');
  },
};
</script>

<template>
  <div class="carousel position-relative">
    <div
      v-for="(item, index) in slides"
      :key="item"
      class="slide"
      :class="{ active: index === currentIndex }"
    >
      <img :src="`/${item}`" alt="slide" class="rounded-3" />
    </div>
    <div class="arrow arrow-left" @click="manualSlide('prev')">
      <img src="@/assets/img/arrow-left.svg" alt="arrow" />
    </div>
    <div class="arrow arrow-right" @click="manualSlide('next')">
      <img src="@/assets/img/arrow-rigth.svg" alt="arrow" />
    </div>
    <div class="d-flex justify-content-center">
      <div
        v-for="i in slides.length"
        :key="i"
        class="point"
        :class="{ active: i - 1 === currentIndex }"
      ></div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import '@/assets/style/partials/variables';

.carousel {
  .slide {
    display: none;
    max-height: 70vh;
    overflow: hidden;

    img {
      width: 100%;
      height: 70vh;
      object-fit: cover;
    }

    &.active {
      display: block;
    }
  }

  .arrow {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);

    background-color: white;
    border-radius: 50%;

    border: none;
    padding: 0;

    display: flex;
    justify-content: center;
    align-items: center;

    box-shadow: 0 0 0.2rem $black;

    transition: all 0.3s;
    cursor: pointer;

    img {
      height: 2.5rem;
    }

    &:hover {
      box-shadow: 0 0 0.5rem $black;
    }

    &.arrow-right {
      right: 0;
      transform: translate(50%, -50%);
    }

    &.arrow-left {
      left: 0;
      transform: translate(-50%, -50%);
    }
  }

  .point {
    background-color: $black;
    height: 0.7rem;
    width: 0.7rem;

    border-radius: 50%;

    margin: 1rem 0.3rem;

    &.active {
      background-color: $secondary;
    }
  }
}
</style>
