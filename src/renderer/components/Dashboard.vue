<template>
  <h1>Este es el dashboard</h1>
</template>
<script>
  export default {
    created () {
      this.$store.commit('SET_LAYOUT', 'app-layout')
    }
  }
</script>
