<template>
  <section class="hero">
    <h1 class="hero__title">We are creatives</h1>
    <a href="/#about">
      <img
        src="assets/icons/icon-arrow-down.svg"
        alt="arrow-down"
        class="hero__arrow"
      />
    </a>
  </section>
</template>

<style lang="scss">
.hero {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100vw;
  height: 100vh;
  background: url('../../../public/assets/images/mobile/image-header.jpg')
    bottom/cover no-repeat hsla(200, 100%, 62%, 1);
  text-align: center;
  &__title {
    width: 68%;
    margin: 1rem 0 2.8rem 0;
    font: 1.5625rem $fraunces;
    letter-spacing: 8px;
    text-transform: uppercase;
    color: $white;
  }
  &__arrow {
    animation: stretch infinite 2s linear 0s;
  }
}

@keyframes stretch {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.2);
  }
  100% {
    transform: scale(1);
  }
}

@media (min-width: 48em) {
  .hero {
    justify-content: center;
    background-image: url('../../../public/assets/images/desktop/image-header.jpg');
    &__title {
      width: 80%;
      font-size: 2.625rem;
    }
    &__arrow {
      margin: 0 0 3rem 0;
    }
  }
}

@media (min-width: 64em) {
  .hero {
    &__title {
      margin: 0 0 4rem 0;
    }
    &__arrow {
      margin: 0 0 6rem 0;
    }
  }
}
@media (min-width: 83em) {
  .hero {
    &__title {
      margin: 0 0 3rem 0;
    }
    &__arrow {
      margin: 0 0 10.5rem 0;
    }
  }
}

@media (min-width: 90em) {
  .hero {
    &__title {
      margin: 0 0 6.5rem 0;
      font-size: 2.625rem;
    }
    &__arrow {
      margin: 0 0 7rem 0;
    }
  }
}
</style>
