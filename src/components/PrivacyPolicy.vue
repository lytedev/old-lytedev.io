<template lang="jade">

  content-block#privacy-policy(:styles="{ backgroundImage: 'url(\"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAcAAAADCAYAAABfwxXFAAAAVklEQVQIWwXBQQ5AMBBA0V902gQnEScRsbZwBHvXFUssqSjGe2boasUofB9eBCsOK8K67ZhpbHSZZ8o8J1E4QyA+D6kVTN9WeoWDwnm8OO4YeRXSLOMH8/4diwIk8l0AAAAASUVORK5CYII=\")', color: '#fff' }")
    slot
      previous-section.scroll-link(href="#intro")

      p: a.scroll-link(href="#about" v-on:click.prevent="showMainContent") Done here?

      h1.section-head Privacy Policy

      p I'm a freelance software engineer who specializes in web
        | technologies. I work with computers and the internet and love
        | every second of it.

      p: a.scroll-link(href="#about" v-on:click.prevent="showMainContent") Done here?

      next-section.scroll-link(:styles="" href="#footer")

</template>

<script lang="coffee">

  module.exports =
    methods:
      showMainContent: ->
        this.$dispatch('show-content', 'mainContent')

    components:
      jumbotron: require './Jumbotron'
      contentBlock: require './ContentBlock'
      nextSection: require './NextSection'
      previousSection: require './PreviousSection'
      ctaButton: require './Button.vue'

</script>

<style lang="stylus">


</style>
