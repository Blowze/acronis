<template>
  <component :is="type" :class="['text-style', variation]">
    <slot />
  </component>
</template>

<script>
  export default {
    name: "TextStyle",
    props: {
      type: {
        type: String,
        default: "span",
      },

      variation: {
        type: String,
        default: "default",
      },
    },
  }
</script>

<style lang="scss" scoped>
  @import "~assets/scss/config";
  @import "~assets/scss/reset";
  @import "~assets/scss/mixins";

  .text-style {

    &.secondary {
      color: color(secondary);
    }

  }
</style>