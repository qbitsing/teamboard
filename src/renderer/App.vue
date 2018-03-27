<template>
  <div id="app">
    <v-app>
      <component :is="layout"></component>
    </v-app>
  </div>
</template>
<script>
  import SimpleLayout from './components/layouts/simple'
  import AppLayout from './components/layouts/app'
  export default {
    name: 'TeamBoard',
    components: { SimpleLayout, AppLayout },
    created () {
      console.log(this)
    },
    computed: {
      layout () {
        return this.$store.getters.layout
      }
    }
  }
</script>
<style>
  @import url("https://use.fontawesome.com/releases/v5.0.8/css/all.css");
  @import url('https://fonts.googleapis.com/css?family=Roboto:300,400,500,700|Material+Icons');
  ::-webkit-scrollbar {
      width: 7px;
  }
  ::-webkit-scrollbar-track {
    background-color: #303030;
  }
  ::-webkit-scrollbar-thumb {
    background-color: rgba(240, 240, 240, .4);
    border-radius: 8px;
  }
  ::-webkit-scrollbar-button {
     display: none;
  }
</style>
