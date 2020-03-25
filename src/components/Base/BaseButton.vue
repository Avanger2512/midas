<template>
  <button
    type="button"
    name="button"
    class="button">
      <slot></slot>
    </button>
</template>

<script>
export default {
  name: 'BaseButton'
}
</script>

<style lang="scss">
@import '../../assets/styles/variables.scss';

.button {
  display: inline-block;
  vertical-align: middle;
  text-align: center;
  font-weight: bold;
  color: #fff;
  text-transform: uppercase;
  transition: .15s ease-in-out;
  box-sizing: border-box;
  cursor: pointer;

  &__icon {
    display: inline-block;
    vertical-align: middle;
  }

  &_capitalize {
    text-transform: capitalize;
  }

  &_md,
  &_sm {
    border-style: solid;
    border-color: transparent;
    width: 100%;
  }

  &_md {
    font-size: 16px;
    border-width: 3px;
    padding: 20px 10px;
    max-width: 226px;
  }

  &_sm {
    font-size: 12px;
    border-width: 2px;
    padding: 16px 5px 15px;
    max-width: 167px;
  }

  &_xs {
    font-size: 12px;
    letter-spacing: 1px;
    line-height: 1.4;
    width: auto;

    path {
      transition: .15s ease-in-out;
    }

    &:hover {
      color: $blue-darker;

      path {
        fill: $blue-darker;
        stroke: $blue-darker;
      }
    }

    &:active {
      color: $blue-dark;

      path {
        fill: $blue-dark;
        stroke: $blue-dark;
      }
    }
  }

  &_primary {
    background: $blue;

    &:hover {
      background: $blue-darker;
    }

    &:active {
      background: $blue-dark;
    }
  }

  &_ghost {
    background: transparent;
    border-color: $blue;
    color: $blue;

    &:hover {
      background: $blue;
      color: #fff;
    }

    &:active {
      background: $blue-darker;
      border-color: $blue-darker;
    }
  }

  &_white {
    background: #fff;
    color: #000;

    &:hover {
      background: $gray-light;
    }

    &:active {
      background: $gray;
    }
  }

  &_danger {
    background: transparent;
    border-color: $red;
    color: $red;

    &:hover {
      background: $red;
      color: #fff;
    }

    &:active {
      background: $red-darker;
      border-color: $red-darker;
    }
  }

  &_ghost-white {
    background: transparent;
    border-color: #fff;
    color: #fff;

    &:hover {
      background: $blue-darker;
      color: #fff;
    }

    &:active {
      background: $blue-dark;
    }
  }

  &:disabled:not(.button_white),
  &.is-disabled:not(.button_white) {
    background: $rgba-white-0-7;
    color: $rgba-white-0-22;
    cursor: default;
  }

  &:disabled:not(.button_primary),
  &.is-disabled:not(.button_primary) {
    background: $gray-light2;
    color: $gray-darker;
    cursor: default;
  }

  &_text-blue {
    color: $blue;
  }

  &_text-white {
    color: #fff;
  }

  &_text-gray {
    color: $gray;
  }

  &_hover-underline {
    position: relative;

    &:after {
      content: '';
      position: absolute;
      left: 0;
      right: 0;
      top: calc(100% - 2px);
      height: 1px;
      opacity: 0;
      background: currentColor;
      transition: opacity .15s ease-in-out;
    }

    &:hover {
      &:after {
        opacity: 1;
      }
    }
  }

}
</style>
