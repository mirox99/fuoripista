<template>
  <div class="home">
    <Header/>
    <product-slider/>
    <Footer/>
  </div>
</template>

<script>
import Header from '@/components/Header'
import ProductSlider from '@/components/ProductSwiper'
import Footer from '@/components/Footer'
import init from '@/helper/smooth'

export default {
  name: 'Home',
  components: {ProductSlider, Header, Footer},
  mounted() {
    this.$nextTick(() => {
      init(this)
    })
  }
}
</script>

<style lang="scss" scoped>
.home {
  width: 100%;
  height: 100vh;
  background-color: #0d0d0d;
}
</style>