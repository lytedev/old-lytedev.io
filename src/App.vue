<template lang="jade">

  #app
    jumbotron
    hello

</template>

<script lang="coffee">

  module.exports =
    components:
      jumbotron: require './components/Jumbotron'
      hello: require './components/Hello'

</script>

<style lang="stylus">

  @import url(https://cdnjs.cloudflare.com/ajax/libs/normalize/3.0.3/normalize.css)
  @import url(https://fonts.googleapis.com/css?family=Lato:400,100,300,700)
  @import url(https://maxcdn.bootstrapcdn.com/font-awesome/4.5.0/css/font-awesome.min.css)

  *, *::before, *::after
    box-sizing border-box

  body
    font-family Lato, sans-serif

</style>
