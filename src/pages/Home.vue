<template>
  <div>
    <Header />
    <div class="album py-5 bg-light">
      <div class="container">
        <div class="row">
          <div class="col-md-12 mb-4 input-group">
            <input type="text" class="form-control" placeholder="Search" @keyup="search($event.target.value)" />
          </div>
          <div class="col-md-4" v-for="(product, i) in products" :key="i">
            <div class="card mb-4 shadow-sm">
              <img :src="product.img" height="200" />
              <div class="card-body">
                <p class="card-text">{{ product.title }}</p>
                <div class="d-flex justify-content-between align-items-center">
                  <small class="text-muted">${{ product.price }}}</small>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import axios from "axios";

export default {
  name: "Home",

  components: {
    Header,
  },

  data() {
    return {
      products: []
    }
  },

  async mounted() {
    await this.load();
  },

  methods: {
    async load(text = '') {
      const { data } = await axios.get(`products?s=${text}`);
      this.product = data.data;
    },
    
    async search(text) {
      await this.load(text);
    }
  }

}
</script>