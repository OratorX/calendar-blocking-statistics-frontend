<template>
  <section>
    <div v-if="$route.query.message" class="alert alert-danger mb-2">
      Need login first
    </div>
    <form @submit.prevent="onSubmit()">
      <h1>Login page</h1>
      <p>
        <nuxt-link to="/">To home page</nuxt-link>
      </p>
      <button class="btn btn-primary" type="submit">Login</button>
    </form>
  </section>
</template>

<script>
export default {
  name: "LoginPage",
  layout: "empty",
  methods: {
    onSubmit() {
      this.$auth.loginWith("google");
      this.$router.push("/");
    },
  },
};
</script>

<style scoped>
form {
  width: 500px;
  margin: 0 auto;
}
</style>
