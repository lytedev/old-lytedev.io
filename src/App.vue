<template lang="jade">

  #app
    header
      jumbotron
      hello

    content-block
      h1 Hello! My name is Daniel and I live in Kansas City, Missouri.

      p I work with computers and the internet and love every second.

      p The internet is a universe of opportunity. I have a knack and a passion for building powerfully useful experiences that can greatly simplify lives or simply draw a crowd.

      p Technology is an ever-changing and constantly-shifting field of work. I relish in the quick-moving world of deprecation and development cycles and am constantly searching for and trying to create the next "best thing."

      p So this isn't just a job for me.

      h2 I thrive here!

</template>

<script lang="coffee">

  module.exports =
    components:
      jumbotron: require './components/Jumbotron'
      contentBlock: require './components/ContentBlock'

</script>

<style lang="stylus">

  @import url(https://cdnjs.cloudflare.com/ajax/libs/normalize/3.0.3/normalize.css)
  @import url(https://fonts.googleapis.com/css?family=Lato:400,100,300,700)
  @import url(https://maxcdn.bootstrapcdn.com/font-awesome/4.5.0/css/font-awesome.min.css)

  *, *::before, *::after
    box-sizing border-box

  body
    font-family Lato, sans-serif

  a
    cursor pointer

  header
    a
      color #eee

</style>
