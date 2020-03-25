<template>
  <div id="app">

    <the-header-desktop />
    <br>
    <br>

    <div class="container">
      <div class="row">
        <div class="column">
          <div class="content">
            <the-header-mobile
              :links="menuLinksFirstLogin" />
          </div>
        </div>
        <div class="column">
          <div class="content">
            <the-header-mobile
              :links="menuLinksFirst" />
          </div>
        </div>
      </div>

      <br>
      <br>
      <br>
      <br>

      <div class="row">
        <div class="column">
          <div class="content">
            <the-header-mobile
              :anotherType="true"
              :signIn="true"
              :links="menuLinksSecond" />
          </div>

        </div>
        <div class="column">
          <div class="content">
            <the-header-mobile
              :anotherType="true"
              :links="menuLinksSecond" />
          </div>
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

        <div class="">
          <base-button
            class="button_md button_primary">BTN BIG</base-button>
        </div>

        <br>
        <br>
        <br>
        <br>

        <div class="">
          <base-button
            class="button_md button_ghost">BTN BIG</base-button>
        </div>

        <br>
        <br>
        <br>
        <br>

        <div class="">
          <base-button
            class="button_md button_white">BTN BIG</base-button>
        </div>

        <br>
        <br>
        <br>
        <br>

        <div class="">
          <base-button
            class="button_md button_danger">BTN BIG</base-button>
        </div>

      </div>
    </section>

    <section class="section section_blue">
      <div class="container">
        <base-button
          class="button_md button_ghost-white">BTN BIG</base-button>
      </div>
    </section>

    <section class="section section_black">
      <div class="container">
        <base-button
          class="button_md button_primary" disabled>BTN BIG</base-button>
      </div>
    </section>

    <section class="section">
      <div class="container">
        <base-button
          class="button_md button_white is-disabled">BTN BIG</base-button>
      </div>
    </section>


    <section class="section section_black">
      <div class="container">
        <div class="row">
          <div class="column">
            <base-button
              class="button_sm button_primary">BUTTON</base-button>
          </div>
          <div class="column">
            <base-button
              class="button_xs button_text-blue">button</base-button>
          </div>
        </div>

        <br>
        <br>

        <div class="row">
          <div class="column">
            <base-button
              class="button_sm button_ghost">BUTTON</base-button>
          </div>
          <div class="column">
            <base-button
              class="button_xs button_text-blue button_hover-underline button_capitalize">button</base-button>
          </div>
        </div>

        <br>
        <br>

        <div class="row">
          <div class="column">
            <base-button
              class="button_sm button_white">BUTTON</base-button>
          </div>
          <div class="column">
            <base-button
              class="button_xs button_text-white">button</base-button>
          </div>
        </div>

        <br>
        <br>

        <div class="row">
          <div class="column">
            <base-button
              class="button_sm button_danger">BUTTON</base-button>
          </div>
          <div class="column">
            <base-button
              class="button_xs button_text-white button_hover-underline button_capitalize">button</base-button>
          </div>
        </div>

        <br>
        <br>

        <div class="row">
          <div class="column">
            <the-loader />
          </div>
          <div class="column">
            <base-button
              class="button_xs button_text-blue button_capitalize">
              button
              <span class="button__icon">
                <svg width="12" height="12" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M10.13 9.356v.773H1.87v-8.26H4.178V.9H1.973c-.343 0-.617.082-.804.27-.187.186-.269.46-.269.803v8.143c0 .343.082.599.275.764.188.163.462.22.798.22h8.045c.336 0 .612-.057.802-.22.195-.165.28-.42.28-.764V7.822h-.97v1.534zM11.1 1V.9H5.9v.97h3.475L4.006 7.236l-.07.071.07.07.615.616.071.07.07-.07 5.368-5.367V6.31h.97V1z" fill="#005BE9" stroke="#005BE9" stroke-width=".2"/></svg>
              </span>

            </base-button>
          </div>
        </div>

        <br>
        <br>

        <div class="row">
          <div class="column"></div>
          <div class="column">
            <base-button
              class="button_xs button_text-gray">
              button
            </base-button>
          </div>
        </div>

      </div>
    </section>

  </div>
</template>

<script>

import TheHeaderDesktop from './components/TheHeaderDesktop/TheHeaderDesktop.vue'
import TheHeaderMobile from './components/TheHeaderMobile/TheHeaderMobile.vue'
import Card from './components/Card/Card.vue'
import BaseButton from './components/Base/BaseButton.vue'
import TheLoader from './components/TheLoader/TheLoader.vue'

export default {
  name: 'App',
  components: {
    TheHeaderDesktop,
    TheHeaderMobile,
    Card,
    BaseButton,
    TheLoader,
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
@import './assets/styles/animation.scss';

$column-width: 33.3%;

body {
  font-family: 'Open Sans', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: $primary-gray;
  font-size: 14px;
  line-height: 1.4;
  min-width: 320px;
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

.content {
  position: relative;
  max-width: 320px;
  min-height: 568px;
  background: lighten($black, 10%);

  @media only screen and (max-width: 960px) {
    margin-bottom: 50px;
  }
}

.section {
  padding: 40px;

  &_black {
    background: $black;
  }

  &_blue {
    background: $blue;
  }
}

.row {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;

  @media only screen and (max-width: 960px) {
    flex-direction: column;
  }

  .column {
    max-width: $column-width;
    flex-basis: $column-width;

    @media only screen and (max-width: 960px) {
      max-width: 100%;
      flex-basis: 100%;
      margin-bottom: 20px;
    }
  }
}

</style>
