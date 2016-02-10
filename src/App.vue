<template lang="jade">

  #app
    header
      jumbotron

    content-block#about(:styles="{ backgroundImage: 'url(\"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAcAAAADCAYAAABfwxXFAAAAQklEQVQIWy2MMRGAQBDEkn0vb4UCN/hCASpQggI45hiqNEm8jrWIJIEMaBpg4LnNyhDzoEEF7090X2alS3tQBOGPXzP6C7P9CQ8hAAAAAElFTkSuQmCC\")', color: '#fff' }")
      slot
        previous-section.scroll-link(href="#intro")

        h1.section-head Hello! My name is Daniel and I live in Kansas City,
          | Missouri.

        p I'm a freelance software engineer who specializes in web
          | technologies. I work with computers and the internet and love
          | every second of it.

        next-section.scroll-link(:styles="" href="#belief")

    content-block#belief(:styles="{ backgroundImage: 'url(\"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAcAAAADCAYAAABfwxXFAAAATUlEQVQIWwXBwQ2AMAwEwb1gE6UPvjxpiA4QJVAAEt0iEpsZ7deSc61Ud2wyhIAgMtD5bAkJDCI+xuhIHTOh414zeCnlAw3cJ1preDV+MM8XuG3wAlMAAAAASUVORK5CYII=\")', color: '#fff' }")
      slot
        previous-section.scroll-link(href="#about")

        p The internet is a universe of opportunity. I have a knack and a
          | passion for building powerfully useful experiences that can
          | greatly simplify lives or simply draw a crowd.

        p Technology is an ever-changing and constantly-shifting field of
          | work. I relish in the quick-moving world of deprecation and
          | development cycles and am constantly searching for and trying to
          | create the next cool thing.

        p So this isn't just a job for me.

        h2 I thrive here!

        next-section.scroll-link(:styles="" href="#contact")

    content-block#contact(:styles="{ backgroundImage: 'url(\"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAcAAAADCAYAAABfwxXFAAAAVUlEQVQIWyXDQQpAUBCA4X/Mmzs4hUu4gXtZKldwIJGUsnyJt6As1Ei++qRvaz+PRJxG4jxwpw0NGRoM6arS93XhuS9MjcwUxxFAmiL3YAFEwR34/l5oxxzFTbgXwgAAAABJRU5ErkJggg==\")', color: '#fff', textShadow: '0px 1px 1px rgba(0, 0, 0, 0.5)' }")
      slot
        previous-section.scroll-link(href="#belief")

        p If you're looking for a software engineer or web developer and
          = "need convincing that I'm worth contacting, you can "
          a(target="_blank" href="https://docs.google.com/document/d/1fPVh7DGWDL7TxYdE9Rz5iNSZQrAhlxdFaCuONYgcs64/edit?usp=sharing")
            | find my resume on Google Drive
          = " and "
          a(target="_blank" href="https://github.com/lytedev") my portfolio of public projects and open source on my GitHub profile
          | . Someday, I'll hopefully compile a list of all the non-public
          | projects I've had a hand in.

        p I'm always on the lookout for cool opportunities. If you think
          | you've got one, feel free to at least shoot me an email - especially
          | if you're a business or organization here in Kansas City looking to
          | have website or software work done! If you'd like, here are some
          | links to some of my stuff.

        hr

        cta-button.button--block-if-mobile(href="https://github.com/lytedev")
          slot
            i.fa.fa-github
            = " GitHub"
        cta-button.button--block-if-mobile(href="https://twitter.com/lytedev")
          slot
            i.fa.fa-twitter
            = " Twitter"
        cta-button.button--block-if-mobile(href="mailto:daniel@lytedev.io")
          slot
            i.fa.fa-envelope
            = " Email"
        //-  @lytedev on GitHub
        //-  @lytedev on Twitter
        //-  @lytedev on Telegram
        //-  Email daniel@lytedev.io

        //- hr

        //- next-section.scroll-link(href="#contact")

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
        console.log target
        if target.length
          event.preventDefault()
          jQuery('html, body').animate
            scrollTop: target.offset().top
          , 1000
          return false

  module.exports =
    components:
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
