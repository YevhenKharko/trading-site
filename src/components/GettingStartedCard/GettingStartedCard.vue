<script>
export default {
  props: {
    number: String,
    title: String,
    text: String,
  },
};
</script>

<template>
  <div class="card">
    <h3>{{ number }}</h3>
    <h4>{{ title }}</h4>
    <p>{{ text }}</p>
  </div>
</template>

<style lang="scss">
.card {
  position: relative;
  display: grid;
  background: #fff;
  width: 280px;
  height: 220px;
  font-family: 'Museo Moderno';
  text-align: start;
  padding: 24px;
  border-radius: 60px;
  border: 2px solid #6248ff;

  &:not(:first-child) {
    @media (min-width: 768px) {
      position: relative;
      top: -40%;
    }
  }

  &:nth-child(even) {
    grid-column: 1 / -1;

    @media (min-width: 768px) {
      grid-column: 5 / 8;
    }
  }

  &:nth-child(odd) {
    grid-column: 1 / -1;

    @media (min-width: 768px) {
      grid-column: 1 / 6;
    }
  }

  &:nth-child(3) {
    @media (min-width: 768px) {
      position: relative;
      top: -60%;
    }
  }

  &:nth-child(4) {
    @media (min-width: 768px) {
      position: relative;
      top: -80%;
    }
  }

  @media (min-width: 768px) {
    width: 330px;
    height: 240px;
    padding: 32px;
  }

  @media (min-width: 1200px) {
    width: 490px;
    height: 200px;
    padding: 32px;
  }

  & h3 {
    color: #6248ff;
    font-size: 15px;
    font-weight: 700;
    margin-bottom: 8px;
  }

  & h4 {
    font-size: 24px;
    font-weight: 700;
    margin-bottom: 24px;
  }

  & p {
    font-family: 'Montserrat';
    font-size: 18px;
    line-height: 18px;
  }
}
</style>