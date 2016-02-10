<template lang="jade">

  a.button.button--hollow(href="{{ href }}")
    slot {{ text }}

</template>

<style lang="stylus">

  @require '../assets/styles/mixins'

  .button
    display block
    text-transform uppercase
    cursor pointer
    font-size 120%
    font-weight 300
    margin 0.25em
    text-decoration none
    padding 0.5em 0.8em
    color #333
    border-radius 0.25em
    background-color #eee
    text-shadow 0 0.05em 0.05em #fff

  .button--hollow
    background-color transparent
    border solid 0.05em #eee
    color #eee
    text-shadow 0 0.05em 0.05em rgba(0, 0, 0, 0.6)
    transition-all()

    &:hover
      background-color #eee
      color #333
      text-shadow 0 0.05em 0.05em #fff

  .button--inline
    display inline

  .button--block-if-mobile
    display block

    +first-breakpoint-post-response()
      display inline

</style>

<script lang="coffee">

  module.exports =
    props: [
      'href'
      'text'
    ]

</script>
