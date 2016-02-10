<template lang="jade">

  #app
    jumbotron

    component(:is="currentView" keep-alive)

    content-block#footer(:styles="{ backgroundColor: '#222', color: '#fff', textShadow: '0px 1px 1px rgba(0, 0, 0, 0.5)' }")
      previous-section.scroll-link(href="#contact")

      p Copyright &copy; 2016

      p Daniel Flanagan

      p All rights reserved.

      p: a(href="#privacy-policy") Privacy Policy

</template>

<script lang="coffee">

  jQuery = require 'jquery'

  jQuery ->
    jQuery('a[href*="#"]:not([href="#"])').click (event) ->
      if location.pathname.replace(/^\//, '') == this.pathname.replace(/^\//,'') and location.hostname == this.hostname
        target = jQuery this.hash
        if target.length
          event.preventDefault()
          jQuery('html, body').animate
            scrollTop: target.offset().top
          , 1000
          return false

  module.exports =
    data: ->
      currentView: "mainContent"
    components:
      mainContent: require './components/MainContent.vue'
      privacyPolicy: require './components/PrivacyPolicy.vue'
      jumbotron: require './components/Jumbotron'
      contentBlock: require './components/ContentBlock'
      nextSection: require './components/NextSection'
      previousSection: require './components/PreviousSection'
      ctaButton: require './components/Button.vue'

</script>

<style lang="stylus">

  @require './assets/styles/mixins'

  @import url(https://cdnjs.cloudflare.com/ajax/libs/normalize/3.0.3/normalize.css)
  @import url(https://fonts.googleapis.com/css?family=Lato:400,100,300,700)
  @import url(https://maxcdn.bootstrapcdn.com/font-awesome/4.5.0/css/font-awesome.min.css)

  *, *::before, *::after
    box-sizing border-box

  body
    font-size 16px
    font-family Lato, sans-serif

    +first-breakpoint-post-response()
      font-weight 300
      font-size 24px

  h1, h2, h3
    font-weight 300

  a
    cursor pointer

  hr
    border 0
    border-top solid 1px rgba(255, 255, 255, 0.5)
    margin 2em

  header
    a
      color #eee

  .wrapper
    max-width $max-wrapped-width
    padding 1em
    margin 0 auto

</style>
