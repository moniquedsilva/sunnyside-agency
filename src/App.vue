<template>
  <div class="container">
    <Header />
    <Hero />
  </div>
</template>

<script>
import Header from '@/components/Header'
import Hero from '@/components/Hero'

export default {
  name: 'App',
  components: {
    Header,
    Hero,
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
