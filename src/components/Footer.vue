<template lang="jade">

    content-block#footer(:styles="{ backgroundColor: '#222', color: '#fff', textShadow: '0px 1px 1px rgba(0, 0, 0, 0.5)' }")
      previous-section.scroll-link(href="#contact")

      p Copyright &copy; 2016

      p Daniel Flanagan

      p All rights reserved.

      p: a.scroll-link(href="#privacy-policy" v-on:click.prevent="showPrivacyPolicy") Privacy Policy

</template>

<style lang="stylus">

  @require '../assets/styles/mixins'

</style>

<script lang="coffee">

  module.exports =
    methods:
      showPrivacyPolicy: ->
        this.$dispatch('show-content', 'privacyPolicy')

    components:
      jumbotron: require './Jumbotron'
      contentBlock: require './ContentBlock'
      nextSection: require './NextSection'
      previousSection: require './PreviousSection'
      ctaButton: require './Button.vue'

</script>
