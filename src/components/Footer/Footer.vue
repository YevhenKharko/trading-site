<template>
  <footer class="footer">
    <div class="logo">
      <img src="../../assets/logo.svg" alt="logo">
    </div>

    <div class="list">
      <ul>
        <li>
          <a href="/about">About us</a>
        </li>
        <li>
          <a href="#started">Instructions</a>
        </li>
        <li>
          <a href="#faq">Platforms</a>
        </li>
        <li>
          <a href="#contact">Contact us</a>
        </li>
        <li>
          <a href="#">Sign in</a>
        </li>
        <li>
          <a href="#">Sing up for free</a>
        </li>
      </ul>
    </div>

    <div class="info" id="warnings">
      <h4>Information and high risk warning:</h4>
      <p>Trading with foreign exchange (FX), contract for differences (CFDs) and precious metals carries a high level of
        risk that may not be suitable for all investors. Leverage creates additional risk and loss exposure. Before you
        decide to trade foreign exchange or contract for differences, carefully consider your investment objectives,
        experience level, and risk tolerance.</p>
    </div>

    <div class="info" id="laundering">
      <h4>Legal disclaimer:</h4>
      <p>Forex trading entails significant risks and is not appropriate for all investors. The possibility of incurring
        substantial losses should be taken into account. It is therefore important to understand the possible consequences
        of investing. Traders should weigh their earning potential against the risks involved and act accordingly.
        Interactive Trade Ltd operating under brand and using domenLink domain within the European Economic Area.</p>
    </div>

    <div class="links">
      <ul>
        <li>Copyright 2024, All Right Reserved</li>
        <li>
          <a href="#">Terms and Conditions</a>
        </li>
        <li>
          <a href="#">Privacy Policy</a>
        </li>
        <li>
          <a href="#">Risk warnings</a>
        </li>
        <li>
          <a href="#">Anti-Money Laundering</a>
        </li>
      </ul>
    </div>
  </footer>
</template>

<style lang="scss">
.footer {
  display: grid;
  grid-column: 1 / -1;

  @media (min-width: 768px) {
    grid-template-rows: auto 60px;
  }

  .logo {
    width: 45px;
    height: 16px;
    padding-block: 46px;
    justify-self: center;

    @media (min-width: 1200px) {
      justify-self: unset;
      grid-column: 1 / 2;
      width: 150px;
    }
  }

  .list,
  .links {
    @media (min-width: 1200px) {
      grid-column: 11 / 12;
    }
    ul {
      display: flex;
      flex-direction: column;
      gap: 32px;
      margin-bottom: 32px;

      @media (min-width: 768px) {
        flex-direction: row;
        justify-content: space-between;
        margin-bottom: 40px;
      }

      @media (min-width: 1200px) {
        flex-direction: column;
        justify-content: center;
      }
    }

    a {
      font-family: 'Museo Sans';
      font-weight: 700;
      color: #333;
    }

    a:visited {
      text-decoration: none;
    }
  }

  .links {
    @media (min-width: 1200px) {
      grid-column: 1 / 12;
      grid-row: 2;
    }

    ul {
      gap: 16px;

      @media (min-width: 768px) {
        flex-direction: column;
      }

      @media (min-width: 1200px) {
        flex-direction: row;
      }
    }

    color: #828282;
    text-align: center;
    cursor: pointer;
    font-family: 'Monserrat';
    font-size: 16px;
    line-height: 27px;

    a {
      font-family: 'Monserrat';
      font-size: 16px;
      line-height: 27px;
      color: #828282;
    }
  }

  .info {
    @media (min-width: 768px) {
      max-width: 80%;
      margin: 0 auto;
      text-align: center;
    }

    @media (min-width: 1200px) {
      max-width: 380px;
      text-align: unset;
      grid-column: 3 / 6;
      grid-row: 1;
    }

    h4 {
      font-family: 'Museo Sans';
      font-weight: 700;
      font-size: 18px;
      margin-bottom: 16px;
    }

    p {
      font-family: 'Montserrat';
      font-size: 16px;
      margin-bottom: 24px;
    }
  }
}

#laundering {
  margin-bottom: 32px;

  @media (min-width: 1200px) {
      max-width: 380px;
      text-align: unset;
      grid-column: 7 / 10;
    }

  p {
    margin-bottom: 0;
  }
}</style>