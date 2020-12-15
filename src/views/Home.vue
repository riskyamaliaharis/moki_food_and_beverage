<template>
  <div class="home">
    <b-container>
      <div class="centered">
        <img alt="Vue logo" src="../assets/logo.png" />
        <Navbar />

        <b-card>
          <h5>Interpolation</h5>
          <p>My name is {{ name }}</p>
        </b-card>
        <b-card>
          <h5>Computed</h5>
          <p>Original Message {{ message }}</p>
          <p>Reverse message : {{ reverseMessage }}</p>
        </b-card>
        <b-card>
          <h5>Directive</h5>
          <hr />
          <h6>v-if</h6>
          <div v-if="rule === 1">Kamu adalah Admin</div>
          <div v-else-if="rule === 2">Kamu adalah Admin</div>
          <div v-else>Kamu adalah User</div>
          <h6>v-show</h6>
          <!-- v-show sembunyi kalo tidak memenuhi kondisi -->
          <div v-show="rule === 3">Kamu Bukan Siapa-siapa</div>
          <h6>v-for</h6>
          <ul>
            <!-- Item bentuknya obj -->
            <li v-for="(item, index) in dataProduct" :key="index">
              {{ index }} -
              <h5>{{ item.product_name }}</h5>
              <p>{{ item.product_price }}</p>
            </li>
          </ul>
          <!-- V on : event handling. Short hand = @click-->
          <h6>v-on</h6>
          <button v-on:click="boom()">Click Me!</button>
          <input type="text" v-model="searchData" v-on:keyup.enter="search()" />
          <h6>v-bind</h6>
          <a v-bind:href="rule == 1 ? urlGoogle : urlYoutube"
            >Click Link Google</a
          >
        </b-card>
      </div>
    </b-container>
  </div>
</template>

<script>
// @ is an alias to /src
//1. Import Componenet
import Navbar from '../components/_base/Navbar'

export default {
  //2. Mendaftarkan komponen yang sudah diimport
  components: {
    Navbar
  },
  name: 'Home',
  data() {
    return {
      name: 'Risky Amalia Haris',
      message: 'Hello World',
      rule: 1,
      searchData: '',
      dataProduct: [
        {
          product_name: 'Meja',
          product_price: 5000
        },
        {
          product_name: 'Kursi',
          product_price: 5000
        },
        {
          product_name: 'Lemari',
          product_price: 5000
        }
      ],
      urlGoogle: 'http://google.com',
      urlYoutube: 'http://youtube.com'
    }
  }, //computed : properti untuk memanipulasi data
  computed: {
    reverseMessage: function() {
      return this.message
        .split(' ')
        .reverse()
        .join(' ')
    }
  }, //watch : cara kerja hampir sama dengan computed tapi ada syaratnya, penulisan datanya harus sama
  methods: {
    boom() {
      console.log('Boom !')
      alert('Boom !')
    },
    search() {
      console.log('Process search !')
      console.log(this.searchData)
    }
  }
}
</script>

<style scoped>
.centered {
  text-align: center;
}
</style>
