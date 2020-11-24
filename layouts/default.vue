<template>
  <main>
    <Header />
    <Nuxt /> 
    <Footer />
  </main>
</template>

<script>
import Header from '../components/_partial/header/Header' 
import Footer from '../components/_partial/footer/Footer'

export default {
  name: 'wrapper',
  components: {
    Header, 
    Footer
  }
}
</script>
