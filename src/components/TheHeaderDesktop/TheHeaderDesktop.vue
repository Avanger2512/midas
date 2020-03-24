<template>
  <header class="header">
    <div class="container">
      <div class="header__in">
        <ul class="header__list">
          <li v-for="(item, index) in menuItems"
              :key="index"
            class="header__item">
            <a href="#" class="header__link header__text">
              {{ item }}
            </a>
          </li>
        </ul>
        <a href="/" class="header__logo">
          <img src="@/assets/images/midas-logo.svg" alt="midas-logo">
        </a>
        <div class="header__info">
          <button type="button" class="header__balance header__text">
            0.00347878
            <span class="header__currency">{{ currency }}</span>
          </button>
          <div class="header__profile">
            <div class="header__dropdown">
              <button type="button" class="header__dropdown-btn header__text">

                <span class="header__dropdown-text">
                  {{ userName }}
                </span>

                <span class="header__profile-icon">
                    <svg  data-name="Layer 1" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path data-name="&lt;Path&gt;" fill="none" stroke="#717F94" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20.59 7.66l-8.69 8.68-8.49-8.48"/></svg>
                </span>

              </button>
            </div>

          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'TheHeaderDesktop',
  data() {
    return {
      menuItems: ['Platform', 'Exchange', 'Fline trading bot', 'Burn-out'],
      userName: 'Egor Razzitooo',
      currency: 'BTC'
    }
  }
}
</script>

<style lang="scss">
@import '../../assets/styles/variables.scss';

.header {
  background: $black;
  padding: 28px 0 27px;

  &__in {
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
    justify-content: space-between;
  }

  &__list {
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
  }

  &__item {
    &:not(:last-child) {
      margin-right: 28px;
    }
  }

  &__link {
    &:hover {
      color: #fff;
    }
  }

  &__logo {
    transition: opacity .15s ease;

    &:hover {
      opacity: .8;
    }

    img {
      max-width: 146px;
    }
  }

  &__info {
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
  }

  &__balance {
    margin-right: 28px;

    &:active {
      color: #fff;
    }
  }

  &__dropdown-text {
    max-width: 90px;
    text-overflow: ellipsis;
    overflow: hidden;
    display: inline-block;
    vertical-align: middle;
    white-space: nowrap;
    margin-right: 5px;
  }

  &__dropdown-btn {
    path {
      transition: stroke .15s ease;
    }

    &:active {
      color: #fff;

      path {
        stroke: #fff;
      }
    }
  }

  &__text {
    font-weight: 700;
    font-size: 16px;
    color: $primary-gray;
    transition: color .15s ease;
  }

  &__profile-icon {
    display: inline-block;
    vertical-align: middle;
    margin-right: 5px;

    svg {
      width: 13px;
    }
  }
}
</style>
