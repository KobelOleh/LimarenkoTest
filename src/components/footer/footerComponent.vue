<template>
  <footer class="footer">
    <div class="footer__container">
      <div class="footer__column footer__column--name">
        <h3 class="footer__title">LIMARENKO</h3>
      </div>
      <nav class="footer__column footer__column--policy">
        <ul class="footer__list">
          <li class="footer__list-item">Політика доставки</li>
          <li class="footer__list-item">Політика конфіденційності</li>
          <li class="footer__list-item">Політика повернення коштів</li>
        </ul>
      </nav>
      <address class="footer__column footer__column--contact">
        <ul class="footer__list">
          <li class="footer__list-item">Instagram</li>
          <li class="footer__list-item">limarenko@gmail.com</li>
        </ul>
      </address>
    </div>
  </footer>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'AppFooter',
});
</script>

<style lang="scss" scoped>
.footer {
  height: 125px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 10px;

  &__container {
    display: flex;
    width: 100%;
    max-width: 1200px;
    justify-content: space-between;
    padding: 0 20px;
  }

  &__column {
    flex: 1;
    text-align: center;

    &--name {
      font-size: 18px;
      font-weight: bold;
      color: #333;
    }

    &--policy,
    &--contact {
      display: flex;
      flex-direction: column;
      align-items: flex-start;
    }
  }

  &__title {
    text-align: left;
    font-size: 40px;
    font-family: Cormorant Garamond;
    line-height: 48.44px;
    letter-spacing: 0.2em;
    font-weight: 400;
    margin: 0;
  }

  &__list {
    list-style: none;
    padding: 0;
    margin: 0;
    text-align: left;
  }

  &__list-item {
    font-family: Basis Grotesque Pro;
    font-size: 14px;
    font-weight: 300;
    line-height: 18.07px;
    text-align: left;
    color: #333;
    margin-bottom: 15px;
  }

  @media (max-width: 1100px) {
    flex-direction: column;
    height: auto;

    &__container {
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    &__column {
      width: 100%;
      margin-bottom: 20px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    &__column--name {
      order: 1;
    }

    &__column--contact {
      order: 2;
    }

    &__column--policy {
      order: 3;
    }

    &__list {
      text-align: center;
    }

    &__list-item {
      text-align: center;
    }
  }

  @media (max-width: 650px) {
    &__title {
      font-size: 15px;
      font-weight: 400;
      line-height: 18.17px;
      letter-spacing: 0.2em;
    }

    &__column--name {
      order: 1;
    }

    &__column--contact {
      order: 2;
    }

    &__column--policy {
      order: 3;
    }

    &__list {
      text-align: center;
    }

    &__list-item {
      font-size: 11px;
      font-weight: 300;
      line-height: 14.03px;
    }
  }
}
</style>