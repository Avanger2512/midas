<template>
  <header :class="['header-mobile', {'is-active': isActive, 'header-mobile_mod': anotherType}]">
    <div class="header-mobile__in">
      <a href="/" class="header-mobile__logo">
        <img
          :src="require(`@/assets/images/${imgLogoSrc}.svg`)"
          alt="midas-logo">
      </a>

      <button
        @click="isActive = !isActive"
        type="button"
        class="header-mobile__hamburger">

        <span
          v-for="(i, index) in 4"
          :key="index" />
      </button>
    </div>
    <div v-if="isActive"
         class="header-mobile__menu">
      <ul class="header-mobile__list">
        <li v-for="(link, index) in links"
            :key="index"
            class="header-mobile__item">
          <a href="#" class="header-mobile__link">{{ link }}</a>
        </li>
      </ul>

      <template v-if="anotherType">
        <ul class="header-mobile__list">
          <li class="header-mobile__item">
            <a href="#" class="header-mobile__link is-active">Profile</a>
          </li>
          <li class="header-mobile__item">
            <a href="#" class="header-mobile__link">
              Balance: <span>{{ balance }}</span> {{ currency }}
            </a>
          </li>
          <li class="header-mobile__item">
            <a href="#" class="header-mobile__link">
              Zero fees and Burn-out
            </a>
          </li>
        </ul>
        <ul class="header-mobile__list">
          <li class="header-mobile__item">
            <a href="#" class="header-mobile__link header-mobile__link_sign">
              <img :src="require(`@/assets/images/sign-${signIcon}.svg`)" alt="">
              {{ signText }}
            </a>
          </li>
        </ul>
      </template>
    </div>
  </header>
</template>

<script>

const signObject = {
  in: {
    icon: 'in',
    text: 'Sign in'
  },
  out: {
    icon: 'out',
    text: 'Sign out'
  }
}

export default {
  name: 'TheHeaderMobile',
  props: {
    links: {
      type: Array
    },
    anotherType: {
      type: Boolean
    },
    signIn: {
      type: Boolean,
      default: false
    }
  },
  created() {
    this.changeLogoSrc();
    this.setSignValue();
  },
  data() {
    return {
      isActive: false,
      imgLogoSrc: 'midas-logo-md',
      signIcon: signObject.in.icon,
      signText: signObject.in.text,
      balance: 0.00119196,
      currency: 'BTC'
    }
  },
  methods: {
    changeLogoSrc() {
      if (this.anotherType) {
        this.imgLogoSrc = 'midas-logo-sm'
      }
    },
    setSignValue() {
      if (!this.signIn) {
        this.signIcon = signObject.out.icon
        this.signText = signObject.out.text
      }
    }
  }
}
</script>

<style lang="scss">
@import '../../assets/styles/variables.scss';

.header-mobile {
  $this: &;
  position: relative;

  &__in {
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
    justify-content: space-between;
    padding: 14px 20px 11px;
    background: $black;
    max-width: 280px;
  }

  &__logo {
    transition: opacity .15s ease;

    &:hover {
      opacity: .8;
    }
  }

  &__hamburger {
    position: relative;
    display: inline-block;
    width: 23px;
    height: 20px;
    transform: rotate(0deg);
    transition: .2s ease-in-out;
    cursor: pointer;

    &:hover {
      opacity: .8;
    }

    span {
      display: inline-block;
      position: absolute;
      height: 2px;
      background: #fff;
      width: 100%;
      left: 0;
      transform: rotate(0deg);
      transition: .2s ease-in-out;

      &:nth-child(1) {
        top: 0px;

        .is-active & {
          opacity: 0;
          top: 5px;
        }
      }

      &:nth-child(2),
      &:nth-child(3) {
        top: 8px;
        width: calc(100% - 8px);

        .is-active & {
          width: 100%;
        }
      }

      &:nth-child(2) {
        .is-active & {
          transform: rotate(45deg);
        }
      }

      &:nth-child(3) {
        .is-active & {
          transform: rotate(-45deg);
        }
      }

      &:nth-child(4) {
        top: 16px;
        width: calc(100% - 3px);

        .is-active & {
          opacity: 0;
          top: 10px;
        }
      }
    }
  }

  &__menu {
    position: absolute;
    top: 100%;
    left: 0;
    z-index: 2;
    background: rgba(9, 12, 19, 0.86);
    backdrop-filter: blur(10px);
    max-width: 263px;
    width: 100%;
    padding: 24px 0;

    ul {
      &:not(:first-child) {
        margin-top: 10px;
        padding-top: 10px;
        border-top: 1px solid rgba(255, 255, 255, 0.1);
      }
    }
  }

  &__item {
    padding: 0 20px;

    &:not(:last-child) {
      margin-bottom: 24px;
    }
  }

  &__link {
    font-size: 16px;
    font-weight: 700;
    color: $primary-gray;
    transition: color .15s ease;

    &:hover,
    &.is-active {
      color: #fff;
    }

    span {
      color: #fff;
    }
  }

  &__link_sign {
    display: flex;
    align-items: center;

    img {
      margin-right: 10px;
    }
  }

  &_mod {
    #{$this}__in {
      padding-top: 19px;
      padding-bottom: 17px;
    }
  }
}
</style>
