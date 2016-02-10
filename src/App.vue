<template lang="jade">
  #app
    img.logo(src="./assets/logo.png")
    hello
</template>

<script lang="coffee">
  hello = require './components/Hello'

  module.exports =
    components:
      hello: hello
</script>

<style lang="stylus">
  @import url(https://fonts.googleapis.com/css?family=Lato:400,100,300,700)

  body
    font-family Lato, sans-serif
</style>
