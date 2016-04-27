<template lang="jade">

  #main-content-container
    slot
      content-block#about(:styles="{ backgroundImage: 'url(\"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAcAAAADCAYAAABfwxXFAAAAQklEQVQIWy2MMRGAQBDEkn0vb4UCN/hCASpQggI45hiqNEm8jrWIJIEMaBpg4LnNyhDzoEEF7090X2alS3tQBOGPXzP6C7P9CQ8hAAAAAElFTkSuQmCC\")', color: '#fff' }")
        slot
          previous-section.scroll-link(href="#intro")

          h1.section-head Hello! My name is Daniel and I live in Kansas City,
            | Missouri.

          p I'm a software engineer who specializes in web
            | technologies. I work with computers and the internet and love
            | every second of it.

          next-section.scroll-link(:styles="" href="#belief")

      content-block#belief(:styles="{ backgroundImage: 'url(\"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAcAAAADCAYAAABfwxXFAAAATUlEQVQIWwXBwQ2AMAwEwb1gE6UPvjxpiA4QJVAAEt0iEpsZ7deSc61Ud2wyhIAgMtD5bAkJDCI+xuhIHTOh414zeCnlAw3cJ1preDV+MM8XuG3wAlMAAAAASUVORK5CYII=\")', color: '#fff' }")
        slot
          previous-section.scroll-link(href="#about")

          p The internet is a universe of opportunity. I have a knack and a passion for building powerful and highly useful, usable experiences that can greatly simplify lives or simply draw a crowd.

          p Technology is an ever-changing and constantly-shifting field of work. I relish in the quick-moving world of software development cycles and ever-new and upcoming technologies. I am constantly searching for and trying to create the next cool thing.

          p So this isn't just a job for me.

          h2 I thrive here!

          next-section.scroll-link(:styles="" href="#contact")

      content-block#contact(:styles="{ backgroundImage: 'url(\"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAcAAAADCAYAAABfwxXFAAAAVUlEQVQIWyXDQQpAUBCA4X/Mmzs4hUu4gXtZKldwIJGUsnyJt6As1Ei++qRvaz+PRJxG4jxwpw0NGRoM6arS93XhuS9MjcwUxxFAmiL3YAFEwR34/l5oxxzFTbgXwgAAAABJRU5ErkJggg==\")', color: '#fff', textShadow: '0px 1px 1px rgba(0, 0, 0, 0.5)' }")
        slot
          previous-section.scroll-link(href="#belief")

          p
            = "If you're looking for a software engineer or web developer and "
            = "need convincing that I'm worth contacting, you can "
            a(target="_blank" href="https://docs.google.com/document/d/1fPVh7DGWDL7TxYdE9Rz5iNSZQrAhlxdFaCuONYgcs64/edit?usp=sharing")
              | find my resume on Google Drive
            = " and "
            a(target="_blank" href="https://github.com/lytedev") my portfolio of public projects and open source on my GitHub profile
            | . Someday, I'll hopefully compile a list of all the non-public
            | projects I've had a hand in.

          p I'm always on the lookout for cool opportunities. If you think
            | you've got one, feel free to at least shoot me an email - especially
            | if you're a business or organization looking to
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

</template>

<style lang="stylus">

  @require '../assets/styles/mixins'

</style>

<script lang="coffee">

  module.exports =
    components:
      jumbotron: require './Jumbotron'
      contentBlock: require './ContentBlock'
      nextSection: require './NextSection'
      previousSection: require './PreviousSection'
      ctaButton: require './Button.vue'

</script>
