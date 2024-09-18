<template>
  <header class="header">
    <div class="header__container">
      <div class="header__row">
        <div class="header__nav-container">
          <nav class="nav" v-if="isDesktop">
            <a href="#" class="nav__item">Головна</a>
            <div class="nav__dropdown">
              <button
                  class="nav__dropbtn"
                  @mouseover="storeBtn = true"
                  @mouseleave="storeBtn = false"
              >
                Магазин
                <i :class="storeBtn ? 'mdi mdi-chevron-up' : 'mdi mdi-chevron-down'"></i>
              </button>
              <div class="nav__dropdown-content">
                <a href="#" class="nav__dropdown-item">Категорія 1</a>
                <a href="#" class="nav__dropdown-item">Категорія 2</a>
              </div>
            </div>
            <div class="nav__dropdown">
              <button
                  class="nav__dropbtn"
                  @mouseover="collectionsBtn = true"
                  @mouseleave="collectionsBtn = false"
              >
                Колекції
                <i :class="collectionsBtn ? 'mdi mdi-chevron-up' : 'mdi mdi-chevron-down'"></i>
              </button>
              <div class="nav__dropdown-content">
                <a href="#" class="nav__dropdown-item">Колекція 1</a>
                <a href="#" class="nav__dropdown-item">Колекція 2</a>
              </div>
            </div>
          </nav>
          <div v-else class="nav__dropdown">
            <button class="nav__mobile-btn">
              <img src="./../../assets/burger-menu.svg" alt="Burger menu img"/>
            </button>
            <div class="nav__dropdown-content">
              <a href="#" class="nav__dropdown-item">Головна</a>
              <a href="#" class="nav__dropdown-item">Магазин</a>
              <a href="#" class="nav__dropdown-item">Колекції</a>
            </div>
          </div>
        </div>

        <div class="header__logo">
          <h2 class="header__logo-text">LIMARENKO</h2>
        </div>

        <div class="header__actions">
          <div class="header__actions-row">
            <a v-if="isDesktop" href="#" class="header__btn">UA/UAH</a>
            <a href="#" class="header__btn">Кошик []</a>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Header',
  data() {
    return {
      windowWidth: window.innerWidth,
      collectionsBtn: false,
      storeBtn: false,
    };
  },
  computed: {
    isDesktop(): boolean {
      return this.windowWidth >= 900;
    }
  },
  methods: {
    handleResize() {
      this.windowWidth = window.innerWidth;
    }
  },
  mounted() {
    window.addEventListener('resize', this.handleResize);
  },
  beforeUnmount() {
    window.removeEventListener('resize', this.handleResize);
  }
});
</script>

<style lang="scss" scoped>
@import "headerStyles";
</style>