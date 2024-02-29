<script>
  import Header from '../Header/Header.vue';
  import Hero from '../Hero/Hero.vue';
  import GettingStarted from '../GettingStarted/GettingStarted.vue';
  import Slider from '../Slider/Slider.vue';
  import Faq from '../Faq/Faq.vue';
  import Form from '../Form/Form.vue';
  import Footer from '../Footer/Footer.vue';

  export default {
    components: {
      Header,
      Hero,
      GettingStarted,
      Slider,
      Faq,
      Form,
      Footer,
    },
  }
</script>

<template>
  <main class="container">
    <Header />
    <Hero />
    <GettingStarted />
    <Slider />
    <Faq />
    <Form />
    <Footer />
  </main>
</template>

<style scoped lang="scss">
@import '../../styles/mixins.scss';
.container {
  box-sizing: border-box;
  padding-inline: 20px;

  @include grid(4);
  @include adaptiveGrid;

  @media (min-width: 768px) {
    padding-inline: 40px;
  }

  @media (min-width: 1200px) {
    padding-inline: 120px;
  }
}

</style>