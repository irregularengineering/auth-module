<template>
  <div>
    <b-jumbotron class="text-center">
      <h3>Welcome to Wild Bill's info stash</h3>
      Now with more PII, user, and credit card information!
      <div class="mt-1">
        <template v-if="$auth.$state.loggedIn">
          <b-btn class="ml-3" variant="info" to="/secure">Secure</b-btn>
          <b-btn class="ml-3" variant="danger" @click="$auth.logout()">Logout</b-btn>
        </template>
        <b-btn variant="success" v-else to="/login">Login</b-btn>
      </div>
    </b-jumbotron>

    <div>
      User status:
      <b-badge>{{ $auth.$state.loggedIn ? 'Logged In' : 'Guest' }}</b-badge>
    </div>
  </div>
</template>

<script>
import { version } from '../../../package.json'

export default {
  computed: {
    version: () => version
  }
}
</script>
