<script>
export default {
  props: {
    id: Number,
    name: String,
    position: String,
    quote: String,
    imgUrl: String,
  },
};

</script>


<template>
  <div class="slider__slide slide">
    <div class="slide__info">
      <img :src="imgUrl" alt="author">
      <h4>{{ name }}</h4>
      <h4 class="sup">{{ position }}</h4>
      <blockquote>
        {{ quote }}
      </blockquote>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.slider__slide {
  display: grid;
  transition: left 0.4s ease;
  position: relative;
  z-index: 0;

  @media (min-width: 1200px) {
    grid-column: 5 / 12;
  }
}

.slide {
  &__info {
    display: flex;
    flex-direction: column;
    align-items: center;
    font-size: 18px;
    font-family: 'Museo Moderno';
    color: #333;
    gap: 10px;


    @media (min-width: 1200px) {
      align-items: flex-start;
      grid-column: 11 / 12;
    }

    img {
      width: 73px;
      height: 73px;
    }

    h4 {
      font-weight: 700;
    }

    .sup {
      font-size: 16px;
      font-family: 'Montserrat';
      font-weight: 400;
      margin-bottom: 75px;

      @media (min-width: 1200px) {
        margin-bottom: 20px;
      }
    }

    blockquote {
      position: relative;
      margin-bottom: 40px;
      text-align: center;
      font-weight: 700;
      color: #333;

      @media (min-width: 768px) {
        max-width: 500px;
      }

      @media (min-width: 1200px) {
        text-align: start;
      }

      &::before {
        content: "";
        position: absolute;
        top: -50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 47px;
        height: 40px;
        background: url('../../assets/quote.png');
        background-repeat: no-repeat;
        background-size: cover;
        background-position: center center;

        @media (min-width: 1200px) {
          top: 1px;
          left: -55px;
          transform: none;
        }
      }
    }
  }
}
</style>