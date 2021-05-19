<template>
  <div class="container">
    <template v-if="$auth.loggedIn">
      <div class="w-1/4">
        <span>Welcome {{ $auth.user.name }}</span>
        <button
          type="button"
          class="w-full p-2 border bg-red-600 text-white rounded"
          @click="logout"
        >
          Log Out
        </button>
      </div>
    </template>
    <template v-else>
      <div class="mb-3">
        <button
          type="button"
          class="w-full p-2 border bg-blue-600 text-white rounded"
          @click="login"
        >
          Log In
        </button>
      </div>
    </template>
  </div>
</template>

<script>
export default {
  methods: {
    login() {
      this.$auth.loginWith('auth0')
    },
    logout() {
      this.$auth.logout()
    },
  },
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
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
