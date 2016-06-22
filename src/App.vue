<template lang="jade">

  #app
    jumbotron
    component(:is="currentView" transition="scrollTo" transition-mode="out-in")
    site-footer

</template>

<script lang="coffee">

  Vue = require 'vue'
  jQuery = require 'jquery'

  Vue.transition 'scrollTo',
    css: false
    enter: (el, done) ->
      jQuery('html, body').animate
        scrollTop: jQuery(el).offset().top
      , 1000
    enterCancelled: (el) ->
      jQuery(el).stop()

  module.exports =
    data: ->
      currentView: "mainContent"

    events:
      'show-content': (content, scrollTo) ->
        this.currentView = content
        if scrollTo
          this.$emit 'scroll-to-element', scrollTo

      'scroll-to-element': (selector) ->
        jQuery('html, body').animate
          scrollTop: jQuery(selector).offset().top
        , 1000

    components:
      mainContent: require './components/MainContent.vue'
      privacyPolicy: require './components/PrivacyPolicy.vue'
      jumbotron: require './components/Jumbotron'
      contentBlock: require './components/ContentBlock'
      nextSection: require './components/NextSection'
      previousSection: require './components/PreviousSection'
      ctaButton: require './components/Button.vue'
      siteFooter: require './components/Footer.vue'

</script>

<style lang="stylus">

  @require './assets/styles/mixins'

  @import url(https://cdnjs.cloudflare.com/ajax/libs/normalize/3.0.3/normalize.min.css)
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
