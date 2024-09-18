<template>
  <div class="product-detail">
    <div class="product-detail__info">
      <nav class="product-detail__breadcrumb">
        <span>Головна</span> &mdash;
        <span>Жилети</span> &mdash;
        <span>Vest</span>
      </nav>
      <h1 class="product-detail__title">Vest</h1>
      <p class="product-detail__description">
        Перероблений декорований жилет. Класичний крій. Асиметричний декор - бічна бахрома. Декоративний рукав-крило з
        вінтажної тюлі.
      </p>
      <div class="product-detail__options">
        <div class="product-detail__options-header">
          <div>
            Vest
          </div>
          <div>
            ₴1 000
          </div>
        </div>
        <div class="product-detail__price">
          ₴1 000
        </div>
        <div class="product-detail__sizes">
          <span>Розмір:</span>
          <button class="product-detail__size">XS</button>
          <button class="product-detail__size">S</button>
          <button class="product-detail__size">M</button>
          <button class="product-detail__size">L</button>
          <button class="product-detail__size">XL</button>
        </div>
        <div class="product-detail__colors">
          <span>Колір:</span>
          <button class="product-detail__color">Чорний</button>
          <button class="product-detail__color">Білий</button>
          <button class="product-detail__color">Сірий</button>
          <button class="product-detail__color">Сірий</button>
        </div>
        <button class="product-detail__add-to-cart">
          Додати у кошик
        </button>
        <div class="product-detail__sku">
          SKU: V0423001
        </div>
      </div>
      <button class="product-detail__details-btn" @click="toggleDetails">
        Деталі {{ isDetailsOpen ? '-' : '+' }}
      </button>

      <div v-if="isDetailsOpen" class="product-detail__more-info">
        <ul class="product-detail__more-info-list">
          <li class="product-detail__more-info-item">65% Бавовна, 35% віскоза</li>
          <li class="product-detail__more-info-item">Кожна сорочка унікальна</li>
          <li class="product-detail__more-info-item">Зроблено в Україні</li>
        </ul>
      </div>
    </div>
    <div class="product-detail__image">
      <img src="/src/assets/mainPageImgs/vest-main-page-img.svg" alt="Vest img"/>
      <img src="/src/assets/mainPageImgs/vest-main-page-img.svg" alt="Vest img"/>
      <img src="/src/assets/mainPageImgs/vest-main-page-img.svg" alt="Vest img"/>
      <img src="/src/assets/mainPageImgs/vest-main-page-img.svg" alt="Vest img"/>
    </div>
  </div>
  <div class="recommendation-block">
    <div class="recommendation-title">Те що вам може сподобатись</div>
    <div class="recommendation-items">
      <div class="recommendation-item">
        <img src="/src/assets/mainPageImgs/you_might_like_1_img.svg" alt="Short glove"/>
        <div class="recommendation-item-title">
          <div>
            Рукавчики короткі
          </div>
          <div>
            ₴1 000
          </div>
        </div>
      </div>
      <div class="recommendation-item">
        <img src="/src/assets/mainPageImgs/you_might_like_2_img.svg" alt="Long glove"/>
        <div class="recommendation-item-title">
          <div>
            Рукавчики довгі
          </div>
          <div>
            ₴1 000
          </div>
        </div>
      </div>
      <div class="recommendation-item">
        <img src="/src/assets/mainPageImgs/you_might_like_3_img.svg" alt="Crop vest"/>
        <div class="recommendation-item-title">
          <div>
            Кроп-жилет
          </div>
          <div>
            ₴1 000
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import {defineComponent} from 'vue';

export default defineComponent({
  name: 'ProductDetailComponent',
  data() {
    return {
      isDetailsOpen: false,
    };
  },
  methods: {
    toggleDetails() {
      this.isDetailsOpen = !this.isDetailsOpen;
    },
  },
});
</script>

<style lang="scss" scoped>
@import "contentStyles";
</style>