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
      <a
        href="#"
        :class="
          item.id == 1
            ? ' about__links about__linkLeft'
            : 'about__links about__linkRight'
        "
      >
        <span>Learn More</span></a
      >
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
    align-items: center;
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
    align-items: center;
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
    font-weight: 900;
  }
  &__paragraph {
    font: 0.875rem $barlow;
    color: $dark-gray-blue;
    line-height: 1.7;
  }
  &__links {
    position: relative;
    width: max-content;
    padding: 1rem 0.375rem;
    color: $dark-desaturated-blue;
    font: 1rem $fraunces;
    font-weight: 900;
    letter-spacing: 0.0625rem;
    text-decoration: none;
    text-transform: uppercase;
    &::after {
      border-radius: 5px;
      bottom: 0.875rem;
      content: '';
      display: block;
      height: 0.625rem;
      left: 0;
      opacity: 0.3;
      position: absolute;
      right: 0;
      transition: opacity 0.3s ease-in-out;
    }
    &:hover,
    &:active {
      color: #000;
      &::after {
        opacity: 1;
      }
    }
    span {
      position: relative;
      z-index: 8;
    }
  }
  &__linkLeft::after {
    background-color: $yellow;
  }
  &__linkRight::after {
    background-color: $soft-red;
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
      align-items: flex-start;
      gap: 2rem;
      text-align: left;
    }
    &__right {
      align-items: flex-start;
      gap: 2rem;
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
    &__left {
      width: 28rem;
    }
    &__right {
      width: 28rem;
    }
    &__bgRight {
      background: url('../../../public/assets/images/desktop/image-transform.jpg')
        center/cover no-repeat hsla(50, 99%, 50%, 1);
    }
    &__bgLeft {
      background: url('../../../public/assets/images/desktop/image-stand-out.jpg')
        center/cover no-repeat hsla(7, 99%, 69%, 1);
    }
  }
}

@media (min-width: 92em) {
  .about {
    height: 100vh;
  }
}
</style>
