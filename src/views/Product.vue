<template>
  <div class="product">
    <b-container>
      <div class="centered">
        <Navbar />
      </div>

      <b-row>
        <b-col cols="4" variant="success">col-4</b-col>
        <b-col cols="8" variant="warning">
          <b-col
            xl="3"
            md="4"
            sm="6"
            xs="12"
            v-for="(item, index) in products"
            :key="index"
          >
            <b-card
              :title="item.product_name"
              img-src="https://picsum.photos/600/300/?image=25"
              img-alt="Image"
              img-top
              tag="article"
              style="max-width: 10rem;"
              class="mb-2"
            >
              <b-card-text> Rp {{ item.product_price }} </b-card-text>

              <b-button href="#" variant="primary">Add to Cart</b-button>
              <b-button href="#" variant="success">Update</b-button>
              <b-button href="#" variant="danger">Delete</b-button>
            </b-card>
          </b-col>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import Navbar from '../components/_base/Navbar.vue'
import axios from 'axios'
export default {
  components: { Navbar },
  name: 'Product',
  created() {
    this.getProduct()
  },
  methods: {
    getProduct() {
      axios
        .get('http://localhost:3000/product?page=1&limit=2')
        .then(response => {
          console.log(response)
        })
        .catch(error => {
          console.log(error)
        })
    }
  }
}
</script>

<style scoped>
.centered {
  text-align: center;
}
</style>
