<template lang="jade">

  .jumbotron
    a(href="/"): img.icon(src="../assets/icon.png")
    a(href="/"): img.banner(src="../assets/banner.png")

    .calls-to-action
      cta-button(href="https://google.com" text="About Me")
      cta-button(text="Get In Touch")

    a: i.fa.fa-angle-down.fa-2x

</template>

<style lang="stylus">

  @require '../assets/styles/mixins'

  .jumbotron
    display flex
    flex-direction column
    justify-content center

    height 100vh

    background-color #222
    background-image url('../assets/kc.jpg')
    background-size cover
    text-align center
    padding 3em

    img
      display block
      margin 1em auto

    .icon
      max-width 10%

      +first-breakpoint-response()
        max-width 25%

    .banner
      max-width 50%

      +first-breakpoint-response()
        max-width 100%

    .calls-to-action
      margin-top 3em
      margin-bottom 1.5em

      +first-breakpoint-response()
        display flex
        flex-direction column

    /* +first-breakpoint-response() */

</style>

<script lang="coffee">

  module.exports =
    components:
      ctaButton: require './Button'

</script>
