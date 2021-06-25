<template>
  <component :is="type" :class="['icon',  `icon_name_${name}`, `icon_size_${size}`]" v-html="svg" />
</template>

<script>
  const req = require.context("@/components/Icon/ui/", true, /^\.\/.*\.svg$/)

  export default {
    name: "icon",
    props: {

      name: {
        required: true,
        default: "settings",
      },
      width: {
        type: String,
        default: "none",
      },

      fill: {
        type: String,
        default: "currentColor",
      },

      stroke: {
        type: String,
        default: "none",
      },

      type: {
        type: String,
        default: "span",
      },

      size: {
        type: String,
        default: "full",

      },
    },
    data() {
      return {
        svg: req("./" + this.name + ".svg").replace(/^<svg /,
          `<svg style="fill: ${this.fill}; stroke: ${this.stroke}; width:${this.width};"`),
      }
    }
  }
</script>
<style lang="scss" scoped>
  .icon {
    display: inline-block;
    vertical-align: middle;
    background-position: 50%;
    background-repeat: no-repeat;

    &_size {
      &_xs {
        width: 12px;
        height: 12px;
      }

      &_s {
        width: 16px;
        height: 18px;
      }

      &_m {
        width: 24px;
        height: 24px;
      }

      &_l {
        width: 30px;
        height: 30px;
      }

      &_xl {
        width: 36px;
        height: 36px;
      }

      &_xxl {
        width: 48px;
        height: 48px;
      }

      &_xxxl {
        width: 88px;
        height: 88px;
      }
    }
  }

  svg {
    display: block;
  }
</style>