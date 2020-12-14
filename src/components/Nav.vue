<template>
  <div class="d-flex flex-column flex-md-row align-items-center p-3 px-md-4 mb-3 border-bottom shadow-sm">
    <router-link to="/" class="navbar-brand my-0 mr-md-auto font-weight-normal">
      Influencer
    </router-link>
    <router-link to="/login" class="btn btn-outline-primary">
      Login
    </router-link>
  </div>
</template>

<script>
export default {
  name: "Nav"
}
</script>