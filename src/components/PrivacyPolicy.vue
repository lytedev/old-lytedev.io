<template lang="jade">

  #privacy-policy-container
    slot
      content-block#privacy-policy(:styles="{ backgroundImage: 'url(\"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAcAAAADCAYAAABfwxXFAAAAYklEQVQIWwFXAKj/AYIRxv8pKA8ANYEXAO7e5AD3dtoA6BP+AAc/IQABaBij/xn+HwAAJAUAEfzhAEnXDAD0+PwAyBD5AAF+Mb3/IQYiAB8wBgAWC/EACZLYAA8DFAC2F+IAbmIdl+3RjvwAAAAASUVORK5CYII=\")', color: '#fff' }")
        slot
          previous-section.scroll-link(href="#intro")

          p: a.scroll-link(href="#about" v-on:click.prevent="showMainContent") Done here?

          h1.section-head Privacy Policy

          p Like millions of other websites, I use Google Analytics on lytedev.io. It records data about my visitors -- that's you! It tracks what website you came form to get here, how long you stay, some information about the device you're using to view lytedev.io, and some other information.

          p What do I do with this information? It helps me better understand the kind of people come to my site and what content they’re reading. This allows me to make better decisions about design and writing.

          p Occasionally, I will compile aggregate statistics about the number of visitors this site receives and browsers being used. No personally identifying data is included in this type of reporting.

          p= "All of my activity falls within the bounds of the "
            a(href="http://www.google.com/analytics/terms/us.html" target="_blank") Google Analytics Terms of Service
            | .

          p: a.scroll-link(href="#about" v-on:click.prevent="showMainContent") Done here?

          next-section.scroll-link(:styles="" href="#footer")

</template>

<script lang="coffee">

  module.exports =
    methods:
      showMainContent: ->
        this.$dispatch('show-content', 'mainContent')

    ready: (a, b, c) ->
      console.log a, b, c, "lol"

    components:
      jumbotron: require './Jumbotron'
      contentBlock: require './ContentBlock'
      nextSection: require './NextSection'
      previousSection: require './PreviousSection'
      ctaButton: require './Button.vue'

</script>

<style lang="stylus">


</style>
