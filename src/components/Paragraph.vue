<template>
  <component :is="type" :class="['paragraph', variation]">
    <slot />
  </component>
</template>

<script>
  export default {
    name: "Paragraph",
    props: {
      type: {
        type: String,
        default: "p"
      },
      variation: {
        type: String,
        default: "medium"
      },
    },
  }
</script>

<style lang="scss">
  @import "~assets/scss/config";
  @import "~assets/scss/mixins";

  .paragraph {
    margin: 0;
    padding: 0;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;

    &.large {
      font-size: 18px;
    }

    &.small {
      font-size: 14px;
    }

    a {
      color: color(link);
    }
  }
</style>