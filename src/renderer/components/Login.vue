<template>
  <v-container class="login-container">
    <v-layout row fill-height>
      <v-flex xs6 class="right-side">
          <img src="~@/assets/login.jpg" class="bg">
          <div class="info-content">
                <h1>TEAMBOARD</h1>
                <v-avatar size="170">
                    <img class="logo" src="~@/assets/logo.png" alt="electron-vue">
                </v-avatar>
                <p>This is my awesome slogan!</p>
                <div class="info-developer">
                    <p>Developed by: <strong>Qbits</strong></p>
                    <div class="socials">
                      <v-tooltip v-for="social in socials" :key="social.username" top>
                        <v-btn @click="openBrowser(social.url)" slot="activator" flat icon color="white">
                            <v-icon>{{social.icon}}</v-icon>
                        </v-btn>
                        <span>{{social.username}}</span>
                      </v-tooltip>
                    </div>
                </div>
          </div>
      </v-flex>
      <v-flex xs6 class="login">
        <v-tabs
          v-model="active"
          slider-color="primary"
        >
          <v-tab ripple>Login</v-tab>
          <v-tab ripple>Registrarse</v-tab>
          <v-tab-item>
            <v-layout row>
              <v-flex xs12 sm10 offset-sm1>
                <v-form class="form">
                  <v-text-field
                  label="Username"
                  v-model="loginUsername"
                  prepend-icon="person"
                  ></v-text-field>
                  <v-text-field
                  :append-icon="e1 ? 'visibility' : 'visibility_off'"
                  :append-icon-cb="() => (e1 = !e1)"
                  :type="e1 ? 'password' : 'text'"
                  label="Password"
                  v-model="loginPassword"
                  prepend-icon="lock"
                  ></v-text-field>
                  <v-btn @click="$router.push('/panel')" block color="primary">SEND</v-btn>
                </v-form>
              </v-flex>
            </v-layout>
          </v-tab-item>
          <v-tab-item>
            <v-layout row>
              <v-flex xs10 offset-xs1>
                <v-form class="form">
                  <v-text-field
                  label="Username"
                  v-model="registerUsername"
                  prepend-icon="person"
                  ></v-text-field>
                  <v-text-field
                  label="Email"
                  v-model="email"
                  prepend-icon="email"
                  ></v-text-field>
                  <v-text-field
                  :append-icon="e1 ? 'visibility' : 'visibility_off'"
                  :append-icon-cb="() => (e1 = !e1)"
                  :type="e1 ? 'password' : 'text'"
                  label="Password"
                  v-model="registerPassword"
                  prepend-icon="lock"
                  ></v-text-field>
                  <v-text-field
                  :append-icon="e1 ? 'visibility' : 'visibility_off'"
                  :append-icon-cb="() => (e1 = !e1)"
                  :type="e1 ? 'password' : 'text'"
                  label="Confirm Password"
                  v-model="confirmPassword"
                  prepend-icon="lock"
                  ></v-text-field>
                  <v-btn block color="primary">SEND</v-btn>
                </v-form>
              </v-flex>
            </v-layout>
          </v-tab-item>
        </v-tabs>

      </v-flex>
    </v-layout>
  </v-container>
</template>
<script>
export default {
  data () {
    return {
      active: null,
      loginUsername: null,
      registerUsername: null,
      email: null,
      loginPassword: null,
      registerPassword: null,
      confirmPassword: null,
      socials: [
        {icon: 'fab fa-github', username: '@qbitsing', url: 'https://github.com/qbitsing'}
      ],
      e1: true
    }
  },
  methods: {
    openBrowser (url) {
      this.$electron.shell.openExternal(url)
    }
  },
  created () {
    this.$store.commit('SET_LAYOUT', 'simple-layout')
  }
}
</script>
<style scoped>
 .login-container {
     padding: 0;
     width: 100% !important;
     min-width: 100% !important;
 }
 .right-side {
   overflow: hidden;
   position: relative;
   height: 100vh;
   color: white;
 }
 .bg {
   position: absolute;
   object-fit: cover;
   height: 100%;
   width: 100%;
   z-index: 0;
 }
 .info-developer {
   width: 100%;
   background: rgba(69, 129, 148, 0.7);
   text-align: center;
   padding: 20px;
 }
 .info-content {
    width: 100%;
    position: absolute;
    background: rgba(0, 0, 0, .5);
    padding: 30px;
    display: flex;
    height: 100%;
    align-items: center;
    flex-direction: column;
    justify-content: space-around
 }
 .form {
   padding: 40px 0;
 }
 .login {
   padding: 50px;
 }
 @media screen and (max-height: 570px) {
   .login {
     padding: 0;
   }
 }
 @media screen and (max-width: 800px){
  .login {
     padding: 0;
   }
   .form {
     padding: 20px 0;
   }
   .info-content {
     padding: 0;
   }
 }
</style>
