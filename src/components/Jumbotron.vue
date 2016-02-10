<template lang="jade">

  .jumbotron
    a(href="/" v-on:click.prevent="0"): img.icon(src="../assets/icon.png")
    a(href="/" v-on:click.prevent="0"): img.banner(src="../assets/banner.png")

    .calls-to-action
      cta-button.button--inline.scroll-link(href="/about" text="About Me")
      cta-button.button--inline.scroll-link(href="/contact" text="Get In Touch")

    next-section.scroll-link(href="/about")

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
      nextSection: require './NextSection'

</script>
