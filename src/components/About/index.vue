<template>
  <div id="about" class="about">
    <section
      v-for="item in info"
      :key="item.id"
      :class="item.id == 1 ? 'about__left' : 'about__right'"
    >
      <h2>
        {{ item.title }}
      </h2>
      <p>{{ item.text }}</p>
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
  &__leftSection {
    grid-area: left;
  }
  &__rightSection {
    grid-area: right;
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
  }
}

@media (min-width: 64em) {
  .about {
    grid-template-rows: repeat(2, minmax(585px, 1fr));
  }
}
</style>
