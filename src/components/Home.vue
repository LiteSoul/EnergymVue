<template>
  <v-layout column>
    <v-flex xs12 class="text-xs-center" mt-5>
      <h3>Home page</h3>
    </v-flex>
    <v-flex class="text-xs-center" mt-5>
      <p>This is a user's home page</p>
      <v-btn @click="logOut">LOGOUT</v-btn>
    </v-flex>
  </v-layout>
</template>

<script>
import firebase from 'firebase'

export default {
	methods: {
		logOut() {
			firebase
				.auth()
				.signOut()
				.then(() => this.$router.push('login'))
		}
	}
}
</script>