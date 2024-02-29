<script>
   import Accordion from '../Accordion/Accordion.vue';
   export default {
    components: {
      Accordion,
    },

    data() {
    return {
      cardsData: [
        { id: 1, question: 'How do I change my details?', text: 'We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!' },
        { id: 2, question: 'What platforms will I be able to use?', text: 'We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!' },
        { id: 3, question: 'How do I change my details?', text: 'We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!' },
        { id: 4, question: 'How do I change my details?', text: 'We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!' },
        { id: 5, question: 'How do I change my details?', text: 'We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!' },
        { id: 6, question: 'How do I change my details?', text: 'We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!' },
        { id: 7, question: 'How do I change my details?', text: 'We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!' },
      ],
    };
  },
  }
</script>

<template>
  <section class="questions" id="faq">
    <h2 class="questions__title">Frequently asked questions</h2>
    <div class="faq-container">
      <Accordion 
        v-for="card in cardsData" 
        :key="card.id" 
        :id="card.id"
        :question="card.question" 
        :text="card.text"
        />
    </div>
  </section>
</template>

<style lang="scss">
.faq-container {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.questions {
  display: grid;
  grid-column: 1 / -1;

  &__title {
    display: grid;
    grid-column: 1 / 2;
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
}
</style>