<template>
  <section class="testimonials">
    <h3 class="testimonials__title">Client testimonials</h3>
    <div class="testimonials__clients">
      <article v-for="item in info" :key="item.id">
        <img :src="item.img" :alt="item.name" class="testimonials__img" />
        <p class="testimonials__paragraph">{{ item.text }}</p>
        <h4 class="testimonials__name">{{ item.name }}</h4>
        <span class="testimonials__span">{{ item.profession }}</span>
      </article>
    </div>
  </section>
</template>

<script>
import { information } from './information';

export default {
  data() {
    return {
      info: information,
    };
  },
};
</script>

<style lang="scss">
.testimonials {
  padding: 1.5625rem 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  &__title {
    font: 0.9375rem $fraunces;
    color: hsla(0, 0%, 68%, 1);
    text-transform: uppercase;
    letter-spacing: 0.245em;
    margin: 1.5625rem 0 1.5rem 0;
  }
  &__clients {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    gap: 2.625rem;
    width: 69%;
    margin: 1.5rem 0 1.5625rem 0;
    text-align: center;
  }
  &__img {
    width: 71px;
    border-radius: 50px;
  }
  &__paragraph {
    margin: 25px 0;
    font: 0.875rem $barlow;
    line-height: 24.71px;
    color: hsla(218, 3%, 45%, 1);
  }
  &__name {
    margin: 0 0 1rem 0;
    font: 1.125rem $fraunces;
    color: $dark-desaturated-blue;
  }
  &__span {
    font: 0.75rem $barlow;
    color: hsla(0, 0%, 68%, 1);
  }
}

@media (min-width: 48em) {
  .testimonials {
    &__title {
      font: 1.5rem $fraunces;
      letter-spacing: 0.23em;
      margin: 4.9rem 0 2.375rem 0;
    }
    &__clients {
      align-items: center;
      width: 80%;
      text-align: center;
    }
    &__paragraph {
      width: 345px;
      height: 92px;
      margin: 2rem 0;
      font: 1.125rem $barlow;
      line-height: 30.33px;
    }
    &__name {
      font: 1.375rem $fraunces;
    }
    &__span {
      font: 0.875rem $barlow;
    }
  }
}

@media (min-width: 64em) {
  .testimonials {
    padding: 4.9rem 0;
    &__clients {
      justify-content: space-around;
      flex-direction: row;
      flex-wrap: wrap;
      gap: 2.5rem;
      margin: 2.375rem 0 4.9rem 0;
    }
  }
}

@media (min-width: 75em) {
  .testimonials {
    &__clients {
      justify-content: center;
      flex-direction: row;
      flex-wrap: nowrap;
      gap: 2rem;
    }
  }
}
</style>
