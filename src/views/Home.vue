<template>
  <div class="home">
    <b-container>
      <div class="centered">
        <Navbar />
      </div>
    </b-container>
  </div>
</template>

<script>
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
