<script setup lang="js">
import Container from './components/Container/Container.vue';
</script>

<script lang="js">
  export default {
    components: {
      Container
    },

    data() {
      return {
        amount: 0,

        someArg: '1230',
      }
    },
    methods: {
        increase() {
          this.amount += 1;
          this.someArg = Number(this.someArg) + 1;
        },

        decrease() {
          this.amount -= 1;
          this.someArg = Number(this.someArg) - 1;
        },

    }
  }
</script>

<template>
  <!-- <button @click="increase">+</button>
  <button @click="decrease">-</button>
  <input v-bind:value="someArg" @input="someArg = $event.target.value" type="text" >
  <p>{{ amount }}</p> -->
  <Container />
</template>

<!-- .container {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.card {
  background: white;
  border-radius: 10px;
  padding: 20px;
  margin: 20px;
  position: relative; /* To position the pseudo-elements correctly */
}

/* Create the dotted lines using pseudo-elements */
.card:not(:last-child)::after {
  content: '';
  position: absolute;
  left: 50%;
  bottom: 0;
  width: 2px; /* Line width */
  height: 40px; /* Distance between cards */
  background: r
.card:not(:last-child)::after {
  content: '';
  position: absolute;
  left: 50%;
  bottom: 0;
  width: 2px; /* Line width */
  height: 40px; /* Distance between cards */
  background: repeating-linear-gradient(
    to bottom,
    black 0,
    black 1px,
    transparent 1px,
    transparent 5px /* Dotted line spacing */
  );
  transform: translateX(-50%);
} -->



<!-- window.addEventListener('resize', adjustLines);

function adjustLines() {
  const cards = document.querySelectorAll('.card:not(:last-child)');
  cards.forEach(card => {
    const nextCard = card.nextElementSibling;
    const line = card.querySelector('::after');
    const distance = nextCard.offsetTop - (card.offsetTop + card.offsetHeight);
    line.style.height = `${distance}px`;
  });
}

adjustLines(); -->



