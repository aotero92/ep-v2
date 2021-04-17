<template>
    <div id="app">
    <Navbar/>
    <Slider/>
    <BlogHome />
    <BlogPost/>
    <Footer />
  </div>
</template>

<script>

import Navbar from './components/Navbar.vue'
import Slider from './components/Slider.vue'
import BlogHome from './components/BlogHome.vue'
import BlogPost from './components/BlogPost.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    Slider,
    BlogHome,
    BlogPost,
    Footer
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

