<template>
  <div>
    <Nav />
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

  async mounted() {
    const { data } = await axios.get('user');

    console.log(data);
  }
}
</script>