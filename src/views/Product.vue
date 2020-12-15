<template>
  <div class="home">
    <div class="centered">
      <img alt="Vue logo" src="../assets/logo.png" />
      <Navbar />
      <h1>This is Page {{ name }}</h1>
      <form>
        <input type="text" placeholder="Product Name ..." />
        <br />
        <input type="text" placeholder="Product Price ..." />
        <br />
        <input type="text" placeholder="Category Id ..." />
        <br />
        <input type="text" placeholder="Product Status ..." />
        <br />
        <button type="submit">Save</button>
        <button type="button">Update</button>
      </form>
      <hr />
      <b-container class="bv-example-row">
        <b-row>
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
          <b-col xl="3" md="4" sm="6" xs="12">2 of 3</b-col>
          <b-col xl="3" md="4" sm="6" xs="12">3 of 3</b-col>
        </b-row>
      </b-container>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
//1. Import Componenet
import Navbar from '../components/_base/Navbar'
import axios from 'axios'

export default {
  //2. Mendaftarkan komponen yang sudah diimport
  components: {
    Navbar
  },
  name: 'Home',
  data() {
    return {
      // name: 'Product'
      products: [
        {
          product_id: 1,
          category_id: 1,
          product_name: 'ayam',
          product_price: 5000,
          product_status: 1
        },
        {
          product_id: 2,
          category_id: 1,
          product_name: 'panggang',
          product_price: 6000,
          product_status: 1
        },
        {
          product_id: 3,
          category_id: 1,
          product_name: 'goreng',
          product_price: 7000,
          product_status: 1
        },
        {
          product_id: 4,
          category_id: 1,
          product_name: 'kare',
          product_price: 8000,
          product_status: 1
        }
      ]
    }
  },
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
