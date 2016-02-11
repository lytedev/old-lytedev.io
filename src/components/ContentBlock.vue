<template lang="jade">

  .content-block(v-bind:style="styles")
    .wrapper
      slot

</template>

<style lang="stylus">

  @require '../assets/styles/mixins'

  .content-block
    background-size cover
    text-align center
    min-height 100vh
    display flex
    flex-direction column
    flex-wrap wrap
    justify-content space-around
    text-shadow 0px 1px 1px rgba(0, 0, 0, 0.5)

    p
      a
        cursor pointer
        color inherit
        text-decoration none
        border-bottom dashed 1px #fff


</style>

<script lang="coffee">

module.exports =
  props: [
    'styles'
  ]

</script>

