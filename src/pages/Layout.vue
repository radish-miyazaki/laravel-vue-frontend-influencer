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

export default {
  name: "Layout",
  components: {
    Nav,
  }
}
</script>