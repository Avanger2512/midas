<template>
  <div id="app">

    <the-header-desktop />
    <br>
    <br>

    <div class="container">
      <div class="row">
        <div class="column">
          <the-header-mobile
            :links="menuLinksFirstLogin" />
        </div>
        <div class="column">
          <the-header-mobile
            :links="menuLinksFirst" />
        </div>
      </div>

      <br>
      <br>
      <br>
      <br>

      <div class="row">
        <div class="column">
          <the-header-mobile
            :anotherType="true"
            :signIn="true"
            :links="menuLinksSecond" />
        </div>
        <div class="column">
          <the-header-mobile
            :anotherType="true"
            :links="menuLinksSecond" />
        </div>
      </div>

      <br>
      <br>
      <br>
      <br>

      <section class="section section_black">
        <card />
      </section>

      <br>
      <br>
      <br>
      <br>


    </div>

    <section class="section section_black">
      <div class="container">
        <base-button />
      </div>

    </section>

  </div>
</template>

<script>

import TheHeaderDesktop from './components/TheHeaderDesktop/TheHeaderDesktop.vue'
import TheHeaderMobile from './components/TheHeaderMobile/TheHeaderMobile.vue'
import Card from './components/Card/Card.vue'
import BaseButton from './components/Base/BaseButton.vue'

export default {
  name: 'App',
  components: {
    TheHeaderDesktop,
    TheHeaderMobile,
    Card,
    BaseButton,
  },
  data() {
    return {
      menuLinksFirstLogin: ['Platform', 'Profile', 'BTC balance', 'My profits', 'Fline trading  bot', 'Midas coin', 'Sign out'],
      menuLinksFirst: ['Platform', 'Fline trading  bot', 'Midas coin', 'Sign in'],
      menuLinksSecond: ['Platform', 'Exchange', 'Fline trading  bot', 'Burn-out']
    }
  }
}
</script>

<style lang="scss">

@import './assets/styles/variables.scss';
@import './assets/styles/reset.scss';

body {
  font-family: 'Open Sans', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: $primary-gray;
  font-size: 14px;
  line-height: 1.4;
}

a {
	text-decoration: none;
}

img {
  max-width: 100%;
}

button {
  background: transparent;
  border: none;
  cursor: pointer;

  &:focus {
    outline: none;
  }
}

.container {
  max-width: 1200px;
  padding: 0 20px;
  margin: 0 auto;
}

.section {
  padding: 40px;

  &_black {
    background: $black;
  }
}

.row {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;


  .column {
    max-width: 50%;
    flex-basis: 50%;
  }
}

</style>
