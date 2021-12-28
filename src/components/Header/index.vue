<template>
  <header class="header">
    <div class="header__nav">
      <a href="/#">
        <img src="assets/icons/logo.svg" alt="Logo" class="header__logo" />
      </a>
      <button class="header__hamburguer" @click="toggleLinks">
        <img src="assets/icons/icon-hamburger.svg" alt="Hamburger Menu" />
      </button>
    </div>
    <nav class="nav">
      <div
        role="image"
        class="nav__triangle"
        :style="isActive ? 'height: 23px;' : 'height: 0;'"
      ></div>
      <div
        class="nav__menu"
        :style="isActive ? 'height: 305px;' : 'height: 0;'"
      >
        <ul class="nav__list">
          <li v-for="link in links" :key="link.id">
            <a href="link.local" class="nav__links">{{ link.name }}</a>
          </li>
          <li>
            <a href="#contact" class="nav__button">Contact</a>
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  methods: {
    toggleLinks() {
      this.isActive = !this.isActive
    },
  },
  data() {
    return {
      isActive: false,
      links: [
        { id: 1, name: 'About', local: '#about' },
        { id: 2, name: 'Services', local: '#services' },
        { id: 3, name: 'Projects', local: '#projects' },
      ],
    }
  },
}
</script>

<style lang="scss">
.header {
  display: flex;
  flex-direction: column;
  align-items: center;
  position: fixed;
  padding: 1.75rem 0;
  width: 88%;
  z-index: 10;
  &__nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
  }
  &__hamburguer {
    border-color: transparent;
    outline: transparent;
    background: transparent;
    cursor: pointer;
  }
}

.nav {
  width: 100%;
  text-align: center;
  &__menu {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    height: 0;
    overflow: hidden;
    transition: $transition;
  }
  &__triangle {
    width: 23px;
    height: 0px;
    margin-left: auto;
    margin-top: 28px;
    background: linear-gradient(
      to bottom right,
      transparent 0%,
      transparent 50%,
      $white 50%,
      $white 100%
    );
    transition: $transition;
  }
  &__list {
    width: 100%;
    list-style-type: none;
    margin: 0;
    padding: 0;
    background-color: $white;
    text-align: center;
  }
  &__list li {
    margin: 2rem 0;
  }
  &__links {
    display: block;
    font: $size $barlow;
    color: $dark-gray-blue;
    text-decoration: none;
    transition: $transition;
  }
  &__button {
    display: block;
    width: 140px;
    border-radius: 1.875rem;
    margin: 0 auto;
    padding: 18px 0;
    background-color: $yellow;
    font: 1rem $fraunces;
    color: $dark-desaturated-blue;
    text-transform: uppercase;
    text-decoration: none;
    text-align: center;
    transition: $transition;
  }
}

@media (min-width: 48em) {
  .header {
    flex-direction: row;
    justify-content: center;
    width: 92.36%;
    &__hamburguer {
      display: none;
    }
  }
  .nav {
    &__menu {
      height: auto !important;
    }
    &__triangle {
      display: none;
    }
    &__list {
      background-color: transparent;
      display: flex;
      justify-content: flex-end;
      align-items: center;
      gap: 3.125rem;
    }
    &__list li {
      margin: 0;
    }
    &__links {
      color: $white;
    }
    &__links:hover {
      transform: scale(1.1);
    }
    &__button {
      background-color: $white;
    }
    &__button:hover {
      color: $white;
      background-color: hsla(200, 100%, 72%, 1);
    }
  }
}

@media (min-width: 120em) {
  .header {
    width: 83.125rem;
  }
}
</style>
