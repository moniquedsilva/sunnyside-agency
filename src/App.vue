<template>
  <div class="container">
    <Header />
    <main>
      <Hero />
      <About />
      <Services />
      <Testimonials />
    </main>
  </div>
</template>

<script>
import Header from '@/components/Header'
import Hero from '@/components/Hero'
import About from '@/components/About'
import Services from '@/components/Services'
import Testimonials from '@/components/Testimonials'

export default {
  name: 'App',
  components: {
    Header,
    Hero,
    About,
    Services,
    Testimonials,
  },
}
</script>

<style lang="scss">
body {
  width: 100%;
  overflow-x: hidden;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: 100vh;
  width: 100%;
}

@media (min-width: 90em) {
  body {
    display: flex;
    justify-content: center;
  }
  .container {
    width: $desktop;
  }
}
</style>
