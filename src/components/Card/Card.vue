<template>
  <div class="card">
    <div class="card__header">
      <div class="card__header card__column">
        <currency
          coinName="dash"
          class="card__currency"/>

        <div class="card__text">
          <span>ROI</span>
          75%
        </div>
      </div>
    </div>

    <div class="card__content">
      <div class="card__title">
        $<span>1 183.74</span>
      </div>
      <div class="card__text">
        17.55 <span>Dash</span>
      </div>
    </div>

    <div class="card__footer card__column">
      <div class="card__text">
        0.17 <span>USD/DAY</span>
      </div>
      <div class="card__text card__text_up">
        +4.43%
        <div class="card__icon"></div>
      </div>
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
@import '../../assets/styles/variables.scss';

.card {
  $this: &;
  max-width: 251px;
  padding: 30px;
  background: rgba(17, 26, 40, 0.85);
  backdrop-filter: blur(15px);
  box-sizing: border-box;

  &__column {
    display: flex;
    flex-flow: row nowrap;
    align-items: flex-start;
    justify-content: space-between;
  }

  &__header,
  &__content {
    margin-bottom: 38px;
  }

  &__title {
    font-size: 18px;
    color: #fff;
    font-weight: bold;

    & > span {
      font-size: 24px;
      margin-left: 3px;
    }
  }

  &__text {
    color: #fff;
    line-height: 1.6;

    & > span {
      color: $rgba-white-5;
      text-transform: uppercase;
    }
  }

  &__text_up {
    color: $green;

    #{$this}__icon {
      background: url('~@/assets/images/arr.svg') no-repeat 50% / cover;
    }
  }

  &__icon {
    display: inline-block;
    width: 8px;
    height: 11px;
  }
}
</style>
