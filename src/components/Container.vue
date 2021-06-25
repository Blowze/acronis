<template>
  <component :is="type" class="container">
    <slot />
  </component>
</template>

<script>
  export default {
    name: "Container",
    props: {
      type: {
        type: String,
        default: "div",
      },
    },
  }
</script>

<style lang="scss" scoped>
  @import "~assets/scss/mixins";
  @import "~assets/scss/config";

  .container {
    padding: 0 64px;
    margin: 0 auto;
    max-width: 1440px;

    @include respond-to(xl) {
      max-width: 100%;
    }

    @include respond-to(lg) {
      padding: 0 32px;
    }

    @include respond-to(sm) {
      padding: 0 16px;
    }

  }
</style>