<script setup>
import DisplayEmployees from './components/DisplayEmployees.vue';
import './assets/main.css'
import Header from './components/Header.vue'
import Navbar from './components/Navbar.vue'
import Footer from './components/Footer.vue'

</script>

<template>
  <main>
    <Navbar />
    <Header />
    <DisplayEmployees />
    <Footer />
  </main>
</template>

<style scoped>
main {
  padding: 20px;
}
</style>
