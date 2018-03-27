<template>
  <div id="app">
    <v-app>
      <v-slide-y-transition mode="out-in">
        <router-view></router-view>
      </v-slide-y-transition>
    </v-app>
  </div>
</template>
<script>
  export default {
    name: 'TeamBoard'
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
