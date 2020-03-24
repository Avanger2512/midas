<template>
  <div id="app">

    <the-header-desktop />
    <the-header-mobile />

    <card />
    <base-button />

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
  }
}
</script>

<style lang="scss">

@import './assets/styles/variables.scss';
body {
  font-family: 'Open Sans', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: $primary-gray;
  font-size: 14px;
}

</style>
