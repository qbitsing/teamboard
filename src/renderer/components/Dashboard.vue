<template>
  <div id="app">
      <v-navigation-drawer
        fixed
        :mini-variant="miniVariant"
        :clipped="clipped"
        v-model="drawer"
        app
      >
        <v-list>
          <v-list-tile 
            router
            :to="item.to"
            :key="i"
            v-for="(item, i) in items"
            exact
          >
            <v-list-tile-content>
              <v-list-tile-title v-text="item.title"></v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-navigation-drawer>
      <v-toolbar fixed app :clipped-left="clipped">
        <v-toolbar-side-icon @click.native.stop="drawer = !drawer"></v-toolbar-side-icon>
        <v-toolbar-title v-text="title"></v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn color="primary">
          <v-icon left>person</v-icon>Nmarias38
        </v-btn>
      </v-toolbar>
      <v-content class="contenedor">
        <v-container fluid fill-height>
          <v-slide-y-transition mode="out-in">
            <router-view></router-view>
          </v-slide-y-transition>
        </v-container>
        <v-speed-dial v-model="fab" fixed bottom right direction="top" open-on-hover transition="slide-y-reverse-transition">
        <v-btn v-model="fab" color="primary" slot="activator" fab hover>
          <v-icon>add</v-icon>
          <v-icon>close</v-icon>
        </v-btn>
        <v-tooltip left>
          <v-btn fab small slot="activator">
            <v-icon>fas fa-users</v-icon>
          </v-btn>
          <span>New Team</span>
        </v-tooltip>
        <v-tooltip left>
          <v-btn fab small slot="activator">
            <v-icon>fas fa-address-book</v-icon>
          </v-btn>
          <span>New Personal Board</span>
        </v-tooltip>
        </v-speed-dial>
      </v-content>
  </div>
</template>

<script>
  export default {
    name: 'teamboard',
    data: () => ({
      clipped: false,
      drawer: true,
      fab: false,
      fixed: false,
      items: [
        { icon: 'apps', title: 'Welcome', to: '/' },
        { icon: 'bubble_chart', title: 'Inspire', to: '/inspire' }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'TeamBoard'
    })
  }
</script>
<style>
 .btn__content {
   height: auto;
 }
 .btn__content .icon {
   top: unset !important;
 }
</style>
