<template lang="jade">

  a.next-section(v-bind:style="styles" href="{{ href }}"): i.fa.fa-angle-down.fa-2x

</template>

<style lang="stylus">

  .next-section
    text-align center
    display block
    color rgba(255, 255, 255, 0.5)

</style>

<script lang="coffee">

  module.exports =
    props: [
      'href'
      'styles'
    ]

</script>

