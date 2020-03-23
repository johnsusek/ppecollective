<template>
  <div class="container">
    <div>
      <h1 class="title">
        Chicago PPE Collective
      </h1>

      <h2 class="subtitle">
        Connecting makers with medicial facilities.
      </h2>

      <div v-if="!loggedIn">
        <el-button @click="loginFacebook">Login with Facebook</el-button>
        <el-button @click="loginGoogle">Login with Google</el-button>
      </div>

      <div v-else>
        Logged in as {{ user.name }} ({{ user.email }})
      </div>
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  computed: {
     ...mapState('auth', ['loggedIn', 'user'])
  },
  methods: {
    async loginGoogle() {
      this.$auth.loginWith('google')
    },
    async loginFacebook() {
      this.$auth.loginWith('facebook')
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
