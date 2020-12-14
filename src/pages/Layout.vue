<template>
  <div>
    <Nav :user="user" />
    <main role="main">
      <router-view />
    </main>
  </div>
</template>

<script>
import Nav from "@/components/Nav.vue";
import axios from "axios";

export default {
  name: "Layout",

  components: {
    Nav,
  },

  data() {
    return {
      user: null
    }
  },

  async mounted() {
    const { data } = await axios.get('user');

    this.user = data.data;
  }
}
</script>