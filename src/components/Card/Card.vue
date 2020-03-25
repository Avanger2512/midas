<template>
  <div class="card">
    <div class="card__header">
      <div class="card__header card__column">

        <currency
          coinName="dash"
          class="card__currency" />

      </div>

    </div>
    <div class="card__content">

    </div>
    <div class="card__footer card__column">

    </div>
  </div>
</template>

<script>
import Currency from '../Currency/Currency.vue'

export default {
  name: 'Card',
  components: {
    Currency
  }
}
</script>

<style lang="scss">

</style>
