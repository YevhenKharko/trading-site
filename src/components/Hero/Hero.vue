<template>
  <section class="hero">
    <div class="hero__text">
      <h2>Trade everywhere.<br /> Invest here!</h2>
      <p>
        We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient
        platform for access to global exchanges. You can work anywhere.
      </p>
      <button>Start trading</button>
    </div>
    <div class="hero__image">
      <img src="../../assets/hero.png" alt="diagram">
    </div>
  </section>
</template>

<style scoped lang="scss">
.hero {
  display: grid;
  grid-column: 1 / -1;
  text-align: left;

  @media (min-width: 768px) {
    text-align: center;
  }

  @media (min-width: 1200px) {
    text-align: left;
  }

  &__text {
    grid-column: 1 / -1;

    @media (min-width: 1200px) {
      grid-column: 1 / 6;
    }

    & h2 {
      margin-bottom: 24px;
      font-weight: 700;
      color: #333;
      font-family: 'Museo Moderno';
      font-size: 40px;

      @media (min-width: 768px) {
        margin-bottom: 32px;
        font-size: 64px;
      }
    }

    & p {
      max-width: 500px;
      line-height: 30px;
      font-size: 18px;
      color: #4f4f4f;
      font-family: 'Montserrat';
      margin-bottom: 32px;

      @media (min-width: 768px) {
        margin: 0 auto;
        margin-bottom: 48px;
      }

      @media (min-width: 1200px) {
        margin: unset;
        margin-bottom: 48px;
      }
    }

    & button {
      width: 100%;
      margin-bottom: 32px;
      height: 40px;
      color: #fff;
      background-color: #6248ff;
      font-weight: 700;
      text-transform: uppercase;
      font-size: 14px;
      border-radius: 60px;

      transform: scale(1);
      transition: transform 0.4s ease;

      &:hover {
        transform: scale(1.05);
      }

      @media (min-width: 768px) {
        width: 260px;
        height: 55px;
        margin-bottom: 32px;
      }

      @media (min-width: 1200px) {
        margin-bottom: unset;
      }
    }


  }

  &__image {
    grid-column: 1 / -1;
    width: 280px;
    height: 300px;
    margin: 0 auto;

    @media (min-width: 768px) {
      width: 420px;
      height: 450px;
    }

    @media (min-width: 1200px) {
      grid-column: 8 / 12;
      width: 490px;
      height: 520px;
    }

    & img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
}
</style>