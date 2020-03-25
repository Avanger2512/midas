<template>
  <div class="currency">
    <img
      :src="require(`@/assets/images/currency/${currencyIconSrc}.svg`)"
      :alt="currencyIconSrc"
      class="currency__icon">
    <div class="currency__inn">
      <div class="currency__title">{{ coinName }}</div>
      <div class="currency__desc">{{ coinName }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Currency',
  props: {
    coinName: {
      type: String
    }
  },
  data() {
    return {
      currencyIconSrc: ''
    }
  },
  created() {
    this.getCurrencyIcon();
  },
  methods: {
    getCurrencyIcon() {
      this.currencyIconSrc = this.coinName;
    }
  }
}
</script>

<style lang="scss">
@import '../../assets/styles/variables.scss';

.currency {
  display: flex;
  flex-flow: row nowrap;
  align-items: center;

  &__icon {
    width: 50px;
    height: 50px;
    background-size: cover;
    background-position: 50% 50%;
    margin-right: 15px;
  }

  &__title {
    font-size: 16px;
    color: #fff;
    text-transform: uppercase;
    font-family: Vollkorn;
  }

  &__desc {
    font-size: 14px;
    line-height: 1.6;
    color: $rgba-white-5;
    text-transform: capitalize;

  }
}
</style>
