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
        :text="card.text" />
    </div>
  </section>
</template>

<style lang="scss">
.started {
  display: grid;
  grid-column: 1 / -1;
  margin: 0 auto;

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

  @media (min-width: 768px) {
    column-gap: 90px;
  }

  @media (min-width: 1200px) {
    column-gap: 150px;
  }
}
}
</style>