<template>
  <header class="header">
    <a href="#"><img class="header__logo" src="../../assets/logo.svg" alt="logo"></a>
    <ul class="header__list">
      <li class="link"><a href="#started">How it works</a></li>
      <li class="link"><a href="#about">About</a></li>
      <li class="link"><a href="#started">Instructions</a></li>
      <li class="link"><a href="#faq">Accounts</a></li>
      <li class="link"><a href="#faq">Platforms</a></li>
      <li class="link"><a href="#contact">Contact</a></li>
    </ul>
    <select class="header__language">
      <option value="EN">EN</option>
      <option value="DE">DE</option>
    </select>
    <button class="header__sign">Sign in for free</button>
    <button class="header__burger" @click="handleClick"></button>
  </header>
</template>

<script>
export default {
  methods: {
    handleClick() {
      alert('Burger menu goes here');
    }
  }
};
</script>

<style scoped lang="scss">
@import '../../styles/mixins.scss';

.header {
  display: grid;
  grid-column: 1 / -1;
  height: 80px;
  align-items: center;
  font-family: 'Museo Moderno';

  &__logo {
    width: 45px;
    height: 15px;
    display: block;

    @media (min-width: 768px) {
      display: none;
    }

    @media (min-width: 1200px) {
      display: block;
    }
  }

  &__list {
    display: none;

    @media (min-width: 1200px) {
      display: block;
      display: flex;
      gap: 32px;
      grid-column: 3 / 10;
    }
  }

  &__language {
    display: none;
    cursor: pointer;

    option:hover {
      cursor: pointer;
    }

    @media (min-width: 1200px) {
      display: block;
      grid-column: 10 / 11;
      width: 80px;
      height: 40px;
      border: 1px solid #000;
      border-radius: 60px;
      text-align: center;
    }
  }

  &__sign {
    display: none;

    transform: scale(1);
    transition: transform 0.4s ease;

    &:hover {
      transform: scale(1.05);
    }

    @media (min-width: 768px) {
      justify-self: end;
      grid-column: 7;
      display: block;
      width: 170px;
      height: 40px;
      color: #fff;
      background-color: #6248ff;
      font-weight: 700;
      text-transform: uppercase;
      font-size: 14px;
      border-radius: 60px;
    }

    @media (min-width: 1200px) {
      justify-self: end;
      grid-column: 12;

    }
  }

  &__burger {
    display: block;
    justify-self: end;
    width: 24px;
    height: 24px;
    background: transparent url('../../assets/burger.svg') no-repeat center center;
    transition: transform 0.4s ease;
    grid-column: 4;

    &:hover {
      transform: scale(1.1);
    }

    @media (min-width: 768px) {
      grid-column: 8;
    }

    @media (min-width: 1200px) {
      display: none;
    }
  }
}

.link {
  height: 100%;
  position: relative;

  a {
    padding-block: 50%;
    color: #333;
    font-weight: 700;
    font-size: 15px;
    transition: color 0.4s ease;
    color: #333;

    &::after {
      content: '';
      width: 100%;
      left: -2000%;
      height: 1px;
      bottom: -10px;
      background: #000;
      position: absolute;
      transition: left 0.4s ease;
    }

    &:hover {
      color: #000;

      &::after {
        left: 0;
      }
    }
  }
}
</style>