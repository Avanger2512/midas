<template>
  <div class="loader">
    <div class="loader__icon"></div>
  </div>
</template>

<script>
export default {
  name: 'TheLoader',

}
</script>

<style lang="scss">
.loader {
  display: flex;
  flex-flow: row nowrap;
  align-items: center;
  justify-content: center;
  width: 99px;
  height: 50px;

  &__icon {
    width: 30px;
    height: 30px;
    background: url('~@/assets/images/loader.png') no-repeat 50% / cover;
    animation: rotation 2s infinite linear;
  }
}

@keyframes rotation { 100% { transform:rotate(360deg); } }
</style>
