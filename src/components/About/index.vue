<template>
  <div id="about" class="about">
    <section
      v-for="item in info"
      :key="item.id"
      :class="item.id == 1 ? 'about__left' : 'about__right'"
    >
      <h2 class="about__title">
        {{ item.title }}
      </h2>
      <p class="about__paragraph">{{ item.text }}</p>
      <a href="#">Learn More</a>
    </section>
    <div role="image" class="about__bgRight"></div>
    <div role="image" class="about__bgLeft"></div>
  </div>
</template>

<script>
import { information } from './information'

export default {
  data() {
    return {
      info: information,
    }
  },
}
</script>

<style lang="scss">
.about {
  display: grid;
  grid-template-rows: repeat(4, minmax(292px, 1fr));
  grid-template-areas:
    'imgRight'
    'left'
    'imgLeft'
    'right';
  &__left {
    grid-area: left;
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 2rem;
    width: 70%;
    margin: 3.125rem auto;
    text-align: center;
  }
  &__right {
    grid-area: right;
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 2rem;
    width: 70%;
    margin: 3.125rem auto;
    text-align: center;
  }
  &__title {
    font: 1.75rem $fraunces;
    color: $dark-desaturated-blue;
    margin: 0;
  }
  &__paragraph {
    font: 0.875rem $barlow;
    color: $dark-gray-blue;
    line-height: 1.7;
  }
  &__bgRight {
    background: url('../../../public/assets/images/mobile/image-transform.jpg')
      center/cover no-repeat hsla(50, 99%, 50%, 1);
    grid-area: imgRight;
  }
  &__bgLeft {
    background: url('../../../public/assets/images/mobile/image-stand-out.jpg')
      center/cover no-repeat hsla(7, 99%, 69%, 1);
    grid-area: imgLeft;
  }
}

@media (min-width: 48em) {
  .about {
    grid-template-rows: repeat(2, minmax(292px, 1fr));
    grid-template-columns: repeat(2, minmax(0, 1fr));
    grid-template-areas:
      'left imgRight'
      'imgLeft right';
    &__left {
      gap: 2rem;
      width: 28rem;
      text-align: left;
    }
    &__right {
      width: 28rem;
      text-align: left;
    }
    &__title {
      font: 2.625rem $fraunces;
    }
    &__paragraph {
      font: 1.125rem $barlow;
      line-height: 1.5;
    }
  }
}

@media (min-width: 64em) {
  .about {
    grid-template-rows: repeat(2, minmax(585px, 1fr));
  }
}

@media (min-width: 92em) {
  .about {
    height: 100vh;
  }
}
</style>
