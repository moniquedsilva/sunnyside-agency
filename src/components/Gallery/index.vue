<template>
  <div class="gallery" id="projects">
    <div aria-label="Milkbottles" class="gallery__milkbottles"></div>
    <div aria-label="Orage" class="gallery__orange"></div>
    <div aria-label="Cone" class="gallery__cone"></div>
    <div aria-label="Ice Cubes" class="gallery__cubes"></div>
  </div>
</template>

<style lang="scss">
.gallery {
  display: grid;
  grid-template-rows: repeat(2, minmax(200px, 1fr));
  grid-template-columns: repeat(2, minmax(146px, 1fr));
  &__milkbottles {
    background: url('../../../public/assets/images/mobile/image-gallery-milkbottles.jpg')
      center/cover no-repeat;
  }
  &__orange {
    background: url('../../../public/assets/images/mobile/image-gallery-orange.jpg')
      center/cover no-repeat;
  }
  &__cone {
    background: url('../../../public/assets/images/mobile/image-gallery-cone.jpg')
      center/cover no-repeat;
  }
  &__cubes {
    background: url('../../../public/assets/images/mobile/image-gallery-sugar-cubes.jpg')
      center/cover no-repeat;
  }
}

@media (min-width: 48em) {
  .gallery {
    grid-template-rows: repeat(1, minmax(238px, 1fr));
    grid-template-columns: repeat(4, minmax(146px, 1fr));
  }
}

@media (min-width: 64em) {
  .gallery {
    grid-template-rows: repeat(1, minmax(338px, 1fr));
    grid-template-columns: repeat(4, minmax(146px, 1fr));
  }
}

@media (min-width: 85em) {
  .gallery {
    grid-template-rows: repeat(1, minmax(438px, 1fr));
    grid-template-columns: repeat(4, minmax(330px, 1fr));
  }
}

@media (min-width: 120em) {
  .gallery {
    grid-template-rows: repeat(1, minmax(638px, 1fr));
    grid-template-columns: repeat(4, minmax(351px, 1fr));
  }
}
</style>
