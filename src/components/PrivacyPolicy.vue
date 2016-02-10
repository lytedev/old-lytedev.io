<template lang="jade">

  content-block#about(:styles="{ backgroundImage: 'url(\"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAcAAAADCAYAAABfwxXFAAAAVklEQVQIWwXBQQ5AMBBA0V902gQnEScRsbZwBHvXFUssqSjGe2boasUofB9eBCsOK8K67ZhpbHSZZ8o8J1E4QyA+D6kVTN9WeoWDwnm8OO4YeRXSLOMH8/4diwIk8l0AAAAASUVORK5CYII=\")', color: '#fff' }")
    slot
      previous-section.scroll-link(href="#intro")

      h1.section-head Hello! My name is Daniel and I live in Kansas City,
        | Missouri.

      p I'm a freelance software engineer who specializes in web
        | technologies. I work with computers and the internet and love
        | every second of it.

      next-section.scroll-link(:styles="" href="#belief")

</template>

<script lang="coffee">

  module.exports =
    components:
      jumbotron: require './components/Jumbotron'
      contentBlock: require './components/ContentBlock'
      nextSection: require './components/NextSection'
      previousSection: require './components/PreviousSection'
      ctaButton: require './components/Button.vue'

</script>

<style lang="stylus">


</style>
