<template>
  <div id="app">
    <header-prismic/>
    <router-view/>
    <footer-prismic/>
  </div>
</template>

<script>
import FooterPrismic from './components/FooterPrismic.vue'
import HeaderPrismic from '../components/HeaderPrismic.vue'

export default {
  name: 'App',
  components: {
    FooterPrismic,
    HeaderPrismic
  }
}
</script>

<style>
@import "./assets/css/resetr.css";
@import "./assets/css/common.css";
@import "./assets/css/bootstrap.min.css";
@import url(https://fonts.googleapis.com/css?family=Lato:400,700,900,400italic,700italic);
@import url(https://fonts.googleapis.com/css?family=Lora:400,400italic,700,700italic);
@import url(https://fonts.googleapis.com/icon?family=Material+Icons);
</style>