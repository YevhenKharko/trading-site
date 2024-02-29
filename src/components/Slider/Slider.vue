<script>
import Slide from '../Slide/Slide.vue';
export default {
  components: {
    Slide,
  },

  data() {
    return {
      slidesData: [
        { id: 1, name: 'Albert Abello', position: 'Director of Growth', quote: 'This magical product actually works! It has radically changed the way we build our audiences. Increasing new customer sales by 6x in our most mature market.', imgUrl: './assets/author_1.png' },
        { id: 2, name: 'Your name', position: 'Your Position', quote: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Obcaecati ipsum ad nobis repellendus nostrum, aperiam molestiae dolores voluptates illum! Asperiores!', imgUrl: './assets/author_1.png' },
        { id: 3, name: 'Your name', position: 'Director of Growth', quote: 'This magical product actually works! It has radically changed the way we build our audiences. Increasing new customer sales by 6x in our most mature market.', imgUrl: './assets/author_1.png' },
        { id: 4, name: 'Your name', position: 'Your Position', quote: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Obcaecati ipsum ad nobis repellendus nostrum, aperiam molestiae dolores voluptates illum! Asperiores!', imgUrl: './assets/author_1.png' },
      ],

      currentSlide: 0,
    };
  },

  methods: {
    nextSlide() {
      this.currentSlide = (this.currentSlide + 1) % this.slidesData.length;
    },

    prevSlide() {
      this.currentSlide = (this.currentSlide - 1 + this.slidesData.length) % this.slidesData.length;
    },

    formatCounter(number) {
      return number < 10 ? `0${number}` : number;
    },
  },
}

</script>

<template>
  <section class="slider" id="about">
    <h2 class="slider__title">People love Big Invest</h2>
    <div class="slider__buttons">
      <button class="btn-prev" @click="prevSlide">&lt;</button>
      <button class="btn-next" @click="nextSlide">></button>
    </div>

    <Slide 
      v-for="(slide, index) in slidesData"
      v-show="index === currentSlide"
      :key="slide.id"
      :id="slide.id"
      :name="slide.name"
      :position="slide.position"
      :quote="slide.quote"
      :imgUrl="slide.imgUrl"
      />

    <div class="slider__counter">
      <span>{{ formatCounter(currentSlide + 1) }}</span>
      /
      <span>{{ formatCounter(slidesData.length) }}</span>
    </div>
  </section>
</template>

<style scoped lang="scss">
.slider {
  display: grid;
  grid-column: 1 / -1;
  position: relative;

  &__title {
    display: grid;
    font-size: 40px;
    font-family: 'Museo Moderno';
    font-weight: 700;
    color: #333;
    margin-bottom: 32px;

    @media (min-width: 768px) {
      font-size: 58px;
      max-width: 500px;
    }
  }

  &__wrapper {
    display: flex;
    justify-content: center;
  }

  &__counter {
    display: flex;
    height: 48px;
    justify-content: center;
    align-items: center;
    color: #6248ff;
    font-weight: 700;
    font-size: 15px;

    @media (min-width: 1200px) {
      grid-column: 1 / 12;
    }
  }

  .btn-next,
  .btn-prev {
    z-index: 1;
    position: absolute;
    display: flex;
    justify-content: center;
    align-items: center;
    bottom: 0;
    left: 5%;
    color: #333;
    width: 48px;
    height: 48px;
    border-radius: 50%;
    font-weight: 700;
    font-size: 18px;
    border: 2px solid #333;
    transform: scale(1);
    transition: border 0.4s ease, color 0.4s ease, transform 0.4s ease;

    @media (min-width: 768px) {
      bottom: 30%;
      left: 0;
    }

    @media (min-width: 1200px) {
      bottom: 30%;
      left: 0;
    }

    &:hover {
      border: 2px solid #000;
      color: #000;
      transform: scale(1.1);
    }
  }

  .btn-next {
    left: 80%;

    @media (min-width: 768px) {
      left: calc(100% - 40px);
    }

    @media (min-width: 1200px) {
      left: calc(5% + 40px);
    }
  }

}
</style>