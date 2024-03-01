<script>
import GettingStartedCard from '../GettingStartedCard/GettingStartedCard.vue';

export default {
  components: {
    GettingStartedCard,
  },

  data() {
    return {
      cardsData: [
        { number: '01.', title: 'Register', text: 'Complete the simple registration to get your trading credentials.' },
        { number: '02.', title: 'Verification', text: 'Big Invest is required to verify your identity, upload your documents quickly and get approved in minutes.' },
        { number: '03.', title: 'Deposit funds', text: 'Big Invest accepts credit cards and bank wires. Just use the secure deposit form and follow the steps.' },
        { number: '04.', title: 'Start Trading', text: 'Once your deposit has been credited, you can begin trading instantly. In no time you will see profits rolling into your account.' },
      ],
    };
  },
}
</script>

<template>
  <section class="started" id="started">
    <h2 class="started__title">Getting Started Is Fast & Easy</h2>
    <div class="started__cards">
      <GettingStartedCard 
        v-for="(card) in cardsData"
        :key="card.number"
        :number="card.number"
        :title="card.title"
        :text="card.text"
      />
      <div class="line-1"></div>
      <div class="line-2"></div>
      <div class="line-3"></div>
    </div>
  </section>
</template>

<style lang="scss">
.started {
  display: grid;
  grid-column: 1 / -1;
  margin: 0 auto;
  position: relative;

  &__title {
    grid-column: 1 / 2;
    text-align: start;
    color: #333;
    font-family: 'Museo Moderno';
    font-size: 40px;
    margin-bottom: 24px;
    font-weight: 700;

  @media (min-width: 768px) {
    grid-column: 1 / 6;
    font-size: 56px;
    margin-bottom: 48px;
  }

  @media (min-width: 1200px) {
    margin-bottom: 60px;
  }
}

&__cards {
  margin: 0 auto;
  display: grid;
  grid-column: 1 / -1;
  row-gap: 24px;
  column-gap: unset;
  z-index: 2;

  @media (min-width: 768px) {
    column-gap: 90px;
  }

  @media (min-width: 1200px) {
    column-gap: 150px;
  }
}
}

.line-1,
.line-2,
.line-3 {
  z-index: -1;
  display: none;
  position: absolute;

  @media (min-width: 768px) {
    width: 330px;
    height: 240px;
    top: 19%;
    left: 28%;
    display: block;
    position: absolute;
    background-color: transparent;
    border-radius: 60px;
    border-top: 2px dashed #6248ff;
    border-right: 2px dashed #6248ff;
  }

  @media (min-width: 1200px) {
    display: block;
    width: 490px;
    height: 200px;
    top: 21%;
    left: 34%;
  }
}

.line-2 {
    top: 35%;
    left: 22%;
    border-right: none;
    border-left: 2px dashed #6248ff;

    @media (min-width: 1200px) {
    display: block;
    top: 36%;
    left: 22%;
  }
}

.line-3 {
  top: 53%;
  @media (min-width: 1200px) {
    top: 55%;
    left: 35%;
  }
}
</style>