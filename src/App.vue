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
    }
  }
}
</script>

<template>
  <div id="app" class="app">
    <div v-if='!loggedin' >
      <div class='login login-background'>
          <div class='login-background-overlay'>
              <div class='login-interface'>
                  <img src='../src/assets/logo.png' />
                  <input placeholder="Username:" class='login-input' />
                  <input placeholder="password" class='login-input' type="password" />
                  <div class='login-submit' v-on:click="loggedin = true">Submit</div>
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
