<template lang="jade">

  .jumbotron
    a(href="/"): img.icon(src="../assets/icon.png")
    a(href="/"): img.banner(src="../assets/banner.png")

    .calls-to-action
      cta-button(text="Get In Touch")
      cta-button(href="https://google.com" text="About Me")

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

    .banner
      max-width 50%

    .calls-to-action
      margin-top 3em

    +first-breakpoint-response()
      display none
      height 50vh

</style>

<script lang="coffee">

  module.exports =
    components:
      ctaButton: require './Button'

</script>
