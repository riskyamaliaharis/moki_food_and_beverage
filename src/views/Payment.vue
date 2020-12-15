<template>
  <div class="home">
    <div class="centered">
      <img alt="Vue logo" src="../assets/logo.png" />
      <Navbar />
      <h1>This is Page {{ name }}</h1>
    </div>
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
  data() {
    return {
      dataTesting: 'Vue Data !'
    }
  },
  beforeCreate() {
    console.log('Before created is running !' + this.dataTesting)
  },
  Created() {
    console.log('Created is running !' + this.dataTesting)
  },
  beforeMount() {
    console.log('Before mounted is running !' + this.dataTesting)
    // console.log(document.getElementById('message'))
  },
  beforeMounted() {
    console.log('Mounted is running !' + this.dataTesting)
    // console.log(document.getElementById('message'))
  }
}
</script>

<style scoped>
.centered {
  text-align: center;
}
</style>
