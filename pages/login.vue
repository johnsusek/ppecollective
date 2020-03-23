<template>
  <div>
    <h1>
      Login
    </h1>

    <div>
      Logged in? {{ loggedIn }}
    </div>

    <div>
      {{ user }}
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  computed: {
     ...mapState('auth', ['loggedIn', 'user'])
  }
}
</script>
