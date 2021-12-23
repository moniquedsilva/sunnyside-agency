<template>
  <section class="hero">
    <h1 class="hero__title">We are creatives</h1>
    <img src="assets/icons/icon-arrow-down.svg" alt="arrow-down" />
  </section>
</template>

<script>
/*export default {
  data() {
    return {
      title: 'Hello',
    }
  },
}*/
</script>
<style lang="scss">
.hero {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 26.25rem;
  background: url('../../../public/assets/images/mobile/image-header.jpg')
    center/cover no-repeat;
  text-align: center;
  &__title {
    width: 66%;
    font: 1.5625rem $fraunces;
    letter-spacing: 8px;
    text-transform: uppercase;
    color: $white;
  }
}
</style>
