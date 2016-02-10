<template lang="jade">

  .hello
    h1 {{ msg }}

</template>

<script lang="coffee">

  module.exports =
    data: -> return { msg: 'Hello World!' }

</script>
