<template>
  <div>
    <h1>Sign In</h1>
    <form @submit.prevent="submit">
      <p>Login Form</p>
      <div>
        <label for="email"></label>
        <input type="email" name="email" v-model="form.email" id="email" />
      </div>
      <div>
        <label for="password"></label>
        <input type="password" name="password" v-model="form.password" id="password" />
      </div>
      <button type="submit">SignIn</button>
    </form>
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  name: "signin",
  components: {
    //
  },
  data() {
    return {
      form: {
        email: "",
        password: ""
      }
    };
  },
  methods: {
    ...mapActions({
      signIn: "auth/signIn"
    }),
    submit() {
      this.signIn(this.form)
        .then(() => {
          this.$router.replace({
            name: "dashboard"
          });
        })
        .catch(() => {
          console.log("failed");
        });
    }
  }
};
</script>

<style scoped>
</style>
