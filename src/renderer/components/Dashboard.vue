<template>
  <v-container>
    <v-layout row>
      <h1>You have pending task in this boards...</h1>
    </v-layout>
    <v-layout>
      <v-flex xs6 lm4>
        <v-card>
          <v-card-title class="board-title">
            <div class="headline">Board name</div>
          </v-card-title>
          <v-card-text>
            <v-list subheader>
              <v-list-tile @click="">
                <v-list-tile-content>
                  <v-list-tile-title>Create the langing page</v-list-tile-title>
                  <v-list-tile-sub-title>You and other person</v-list-tile-sub-title>
                </v-list-tile-content>
              </v-list-tile>
              <v-list-tile @click="">
                <v-list-tile-content>
                  <v-list-tile-title>Design the UX...</v-list-tile-title>
                  <v-list-tile-sub-title>You</v-list-tile-sub-title>
                </v-list-tile-content>
              </v-list-tile>
            </v-list>
          </v-card-text>
          <v-card-actions>
            <v-layout row>
              <v-flex xs6>
                <v-btn flat >Team Name</v-btn>
              </v-flex>
              <v-flex xs6>
                <v-icon>fas fa-clock</v-icon>
                <span>16/03/1999</span>
              </v-flex>
            </v-layout>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>
<script>
  export default {
    created () {
      this.$store.commit('SET_LAYOUT', 'app-layout')
    }
  }
</script>
<style>
  .card__text {
    padding: 0 16px !important;
  }
</style>

