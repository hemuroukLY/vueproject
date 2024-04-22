

<template>
<div>
  <Header></Header>
  <Banner></Banner>
  <Feature></Feature>
  <Footer></Footer>
</div>
</template>

<script >
import Header from './components/Header.vue'
import Banner from './components/Banner.vue'
import Feature from './components/Feature.vue'
import Footer from './components/Footer.vue'

export default{
  components:{
    Header,
    Banner,
    Feature,
    Footer,
  }
};
</script>

