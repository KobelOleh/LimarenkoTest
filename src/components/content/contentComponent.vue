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
          <button v-for="size in sizes" class="product-detail__size">{{ size }}</button>
        </div>
        <div class="product-detail__colors">
          <span>Колір:</span>
          <button v-for="color in colors" class="product-detail__color">{{ color }}</button>
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
          <li v-for="info in infoList" class="product-detail__more-info-item">{{ info }}</li>
        </ul>
      </div>
    </div>
    <div class="product-detail__image">
      <img v-for="picture in picturesList" :src="picture" alt="Vest img"/>
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
      sizes:[
        'XS',
        'S',
        'M',
        'L',
        'XL',
      ],
      colors:[
        'Чорний',
        'Білий',
        'Сірий',
        'Сірий'
      ],
      infoList:[
        '65% Бавовна, 35% віскоза',
        'Кожна сорочка унікальна',
        'Зроблено в Україні'
      ],
      picturesList:[
        '/src/assets/mainPageImgs/vest-main-page-img.svg',
        '/src/assets/mainPageImgs/vest-main-page-img.svg',
        '/src/assets/mainPageImgs/vest-main-page-img.svg',
        '/src/assets/mainPageImgs/vest-main-page-img.svg',
      ],
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