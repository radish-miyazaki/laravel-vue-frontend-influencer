<template>
  <div class="d-flex flex-column flex-md-row align-items-center p-3 px-md-4 mb-3 border-bottom shadow-sm">
    <router-link to="/" class="navbar-brand my-0 mr-md-auto font-weight-normal">
      Influencer
    </router-link>
    <nav class="my-2 my-md-0 mr-md-3" v-if="this.isAuthenticated()">
      <router-link to="/stats" class="btn btn-outlined-secondary">
        Stats
      </router-link>
      <router-link to="/rankings" class="btn btn-outlined-secondary">
        Rankings
      </router-link>
      <a href="javascript:void(0)" @click="logout" class="btn btn-outlined-primary">
        Logout
      </a>
    </nav>
    <router-link to="/login" class="btn btn-outline-primary" v-if="!this.isAuthenticated()">
      Login
    </router-link>
    <router-link to="/profile" class="btn btn-outline-primary" v-if="this.isAuthenticated()">
      {{ user?.first_name }} {{ user?.last_name }}
    </router-link>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "Nav",

  methods: {
    async logout() {
      await axios.post('logout', {});

      await this.$router.push('/login');
    },

    isAuthenticated() {
      return this.user?.id;
    }
  },

  computed: {
    user() {
      return this.$store.state.user;
    }
  }

}
</script>