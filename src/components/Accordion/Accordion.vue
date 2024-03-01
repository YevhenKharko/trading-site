<script>
  export default {
    data() {
    return {
      isOpen: false,
    };
  },
  methods: {
    toggleAnswer() {
      this.isOpen = !this.isOpen;
    },
  },
  props: {
    id: Number,
    question: String,
    text: String,
  }, 
}
</script>

<template>
  <div class="faq" @click="() => toggleAnswer()" >
      <div class="header">
          <div class="question">
              {{ question }}
          </div>
          <button class="question__button" :class="{ 'question__button-rotated': isOpen }">+</button>
      </div>
      <div class="answer" :class="{ 'answer__open': isOpen }">
          <p> {{ text }} </p>
      </div>
  </div>
</template>

<style scoped lang="scss">
.faq {
  border: 1px solid #6248ff;
  border-radius: 20px;
  min-height: 100px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 24px 16px;
  
  @media (min-width: 1200px) {
    padding: 32px 40px;
  }

  &:hover {
    cursor: pointer;
  }

  .header {
    display: flex;
    gap: 5px;
    align-items: center;
    justify-content: space-between;
    border-radius: 6px 6px 0 0;
    margin-bottom: 24px;
    cursor: pointer;

    .question {
      font-size: 24px;
      font-family: 'Museo Sans';
      font-weight: 700;

      &__button {
        font-size: 32px;
        font-weight: 700;
        background-color: transparent;
        transition: transform 0.4s ease;
        transform: rotateZ(0deg);

        &-rotated {
        transform: rotateZ(225deg);
        }
      }
    }
  }

  .answer {
    height: 0;
    background-color: transparent;
    transition: height 0.4s ease;
    overflow: hidden;
    font-size: 16px;
    font-family: 'Montserrat';
    text-align: start;
    line-height: 27px;

    p {
      max-width: 90%;

      @media (min-width: 768px) {
        max-width: 560px;
      }

      @media (min-width: 1200px) {
        max-width: 750px;
      }
    }

    &__open {
      height: 350px;
      
      @media (min-width: 768px) {
        height: 160px;
      }

      @media (min-width: 1200px) {
        height: 110px;
      }
    }
  }
}
</style>
