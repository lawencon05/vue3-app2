<template>
  <h2>Welcome, {{ email }}</h2>
  <button @click="goToUser()">User</button>
  <button @click="logout">Logout</button>
</template>

<script>
import { getProfile, clearProfile } from "../services/credential";
import { router } from "../router";

export default {
  name: "Dashboard",
  data() {
    return {
      email: "",
    };
  },
  mounted() {
    this.email = getProfile().email;
  },
  methods: {
    goToUser() {
      router.push({ name: "user" });
    },
    logout() {
      clearProfile();
      router.push({ name: "login" });
    },
  },
};
</script>
