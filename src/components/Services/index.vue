<template>
  <div id="services" class="services">
    <section class="graphic-card">
      <h3 class="graphic-card__title">Graphic design</h3>
      <p class="graphic-card__paragraph">
        Great design makes you memorable. We deliver artwork that underscores
        your brand message and captures potential client's attention.
      </p>
    </section>
    <section class="photography-card">
      <h3 class="photography-card__title">Photography</h3>
      <p class="photography-card__paragraph">
        Increase your credibility by getting the most stunning, high-quality
        photos that improve your business image.
      </p>
    </section>
  </div>
</template>

<style lang="scss">
.services {
  display: grid;
  grid-template-rows: repeat(2, minmax(585px, 1fr));
}

.graphic-card {
  background: url('../../../public/assets/images/mobile/image-graphic-design.jpg')
    top/cover no-repeat hsla(170, 40%, 63%, 1);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-end;
  gap: 1.625rem;
  text-align: center;
  &__title {
    width: 80%;
    font: 1.75rem $fraunces;
    color: $dark-cyan;
    margin: 0;
    font-weight: 900;
  }
  &__paragraph {
    width: 80%;
    height: 6rem;
    font: 0.875rem $barlow;
    color: $dark-cyan;
    line-height: 1.7;
    margin-bottom: 3.125rem;
  }
}

.photography-card {
  background: url('../../../public/assets/images/mobile/image-photography.jpg')
    top/contain no-repeat hsla(197, 99%, 68%, 1);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-end;
  gap: 1.625rem;
  text-align: center;
  &__title {
    width: 72%;
    font: 1.75rem $fraunces;
    color: $dark-desaturated-blue;
    margin: 0;
    font-weight: 900;
  }
  &__paragraph {
    width: 72%;
    height: 6rem;
    font: 0.875rem $barlow;
    color: $dark-desaturated-blue;
    line-height: 1.7;
    margin-bottom: 3.125rem;
  }
}

@media (min-width: 48em) {
  .services {
    grid-template-rows: repeat(1, minmax(588px, 1fr));
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
  .graphic-card {
    background: url('../../../public/assets/images/desktop/image-graphic-design.jpg')
      top/cover no-repeat hsla(170, 40%, 63%, 1);
    gap: 2rem;
    &__title {
      width: 22rem;
      font: 2rem $fraunces;
    }
    &__paragraph {
      width: 22rem;
      font: 1rem $barlow;
      line-height: 1.5;
    }
  }
  .photography-card {
    background: url('../../../public/assets/images/desktop/image-photography.jpg')
      top/cover no-repeat hsla(197, 99%, 68%, 1);
    gap: 2rem;
    &__title {
      width: 22rem;
      font: 2rem $fraunces;
    }
    &__paragraph {
      width: 22rem;
      font: 1rem $barlow;
      line-height: 1.5;
    }
  }
}

@media (min-width: 92em) {
  .services {
    height: 100vh;
  }
  .graphic-card {
    &__title {
      width: 20rem;
      font: 2.625rem $fraunces;
    }
    &__paragraph {
      width: 20rem;
      font: 1.125rem $barlow;
      line-height: 1.5;
      margin-bottom: 6rem;
    }
  }

  .photography-card {
    &__title {
      font: 2rem $fraunces;
    }
    &__paragraph {
      font: 1rem $barlow;
      line-height: 1.5;
      margin-bottom: 6rem;
    }
  }
}
</style>
