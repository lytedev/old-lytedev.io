<template lang="jade">

  .jumbotron#intro
    a(href="/" v-on:click.prevent="0"): img.icon(src="../assets/icon.png")
    a(href="/" v-on:click.prevent="0"): img.banner(src="../assets/banner.png")

    .calls-to-action
      cta-button.button--inline.scroll-link(href="#about" text="About Me")
      cta-button.button--inline.scroll-link(href="#contact" text="Get In Touch")

    next-section.scroll-link(href="#about")

</template>

<style lang="stylus">

  @require '../assets/styles/mixins'

  @keyframes fadeinborder
    0%
      border-color transparent
    75%
      border-color transparent
    100%
      border-color inherit

  @keyframes slideuplate
    0%
      top 25px
    40%
      top 25px
    100%
      top 0px

  @keyframes slideup
    0%
      top 25px
    100%
      top 0px

  @keyframes slidedown
    0%
      top -50px
    100%
      top 0px

  @keyframes fadein
    0%
      opacity 0
    100%
      opacity 1

  @keyframes fadeinlate
    0%
      opacity 0
    50%
      opacity 0
    100%
      opacity 1

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
      position relative
      max-width 10%
      animation fadeinlate 2s, slidedown 2s
      transition-all()

      &:hover
        opacity 0.5

      +first-breakpoint-response()
        max-width 25%

    .banner
      position relative
      max-width 50%
      animation fadein 1s, slideup 1s
      transition-all()

      &:hover
        opacity 0.5

      +first-breakpoint-response()
        max-width 100%

    .calls-to-action
      position relative
      animation fadeinlate 4s, slideuplate 4s
      margin-top 3em
      margin-bottom 1.5em

      .button--hollow
        animation fadeinborder 4s

      +first-breakpoint-response()
        display flex
        flex-direction column

    .next-section
      position relative
      animation fadeinlate 6s, slideuplate 6s

    /* +first-breakpoint-response() */

</style>

<script lang="coffee">

  module.exports =
    components:
      ctaButton: require './Button'
      nextSection: require './NextSection'

</script>
