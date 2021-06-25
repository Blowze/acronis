<template>
  <component :is="level" class="heading">
    <slot />
  </component>
</template>

<script>
  export default {
    name: "Heading",
    props: {
      level: {
        type: String,
        default: "h1",
      },
    },
  }
</script>

<style lang="scss" scoped>
  .heading {
    margin: 0;
  }

  h2 {
    line-height: 32px;
  }
</style>