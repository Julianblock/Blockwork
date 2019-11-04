<script>
// import Login from './components/Login/index';
import Layout from './layout/index.vue'


export default {
  name: 'app',
  components: {
    Layout,
    // Login,
  },
  data () {
    return {
      loggedin: false,
      signUpMode: false,
    }
  },
  methods: {
    signUp() {
      this.signUpMode = true;
    },
    toLogin() {
      this.signUpMode = false;
    },
    addUser() {
      
    }
  }
}
</script>

<template>
  <div id="app" class="app">
    <div v-if='!loggedin && !signUpMode' >
      <div class='login login-background'>
          <div class='login-background-overlay'>
              <div class='login-interface'>
                  <img src='../src/assets/logo.png' />
                  <input placeholder="Username" class='login-input' type="text" />
                  <input placeholder="Password" class='login-input' type="password" />
                  <div class='login-submit' v-on:click="loggedin = true">Submit</div>
                  <div class='sign-up' v-on:click="signUp()">Sign Up</div>
              </div>
          </div>
      </div>
    </div>
    <div v-else-if='!loggedin && signUpMode' >
      <div class='login login-background'>
          <div class='login-background-overlay'>
              <div class='login-interface'>
                  <img src='../src/assets/logo.png' />
                  <div v-if="signUpMode" class="sign-up-back-button" v-on:click="toLogin()">Back</div>
                  <input placeholder="Email" class='login-input' type="text" />
                  <input placeholder="Phone" class='login-input' type="text" />
                  <input placeholder="Username" class='login-input' type="text" />
                  <input placeholder="Password" class='login-input' type="password" />
                  <div class='login-submit' v-on:click="addUser()">Sign Up</div>
                  <div v-if="!signUpMode" class='sign-up' v-on:click="signUp()">Sign Up</div>
              </div>
          </div>
      </div>
    </div>
    <div v-else-if='loggedin'>
    <Layout  />
    <div class='content'>
      <router-view />
    </div>
    </div>
  </div>
</template>


<style lang="scss">
  @import './styles/index.scss';

</style>
