<template>
  <div class="main-page">
    <header-component />
    <div class="scroll-container">
      <Loader v-if="isLoading" />
      <div v-else>
        <content-component />
        <footer-component />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import headerComponent from './header/headerComponent.vue';
import contentComponent from './content/contentComponent.vue';
import footerComponent from "./footer/footerComponent.vue";
import Loader from './ui-helpers/loader/loader.vue';

export default {
  name: 'mainPageComponent',
  components: {
    footerComponent,
    headerComponent,
    contentComponent,
    Loader,
  },
  data() {
    return {
      isLoading: true,
    };
  },
  async mounted() {
    await this.loadContent();
  },
  methods: {
    async loadContent() {
      await new Promise((resolve) => setTimeout(resolve, 2000));
      this.isLoading = false;
    }
  },
};
</script>

<style lang="scss">
.main-page {
  display: flex;
  flex-direction: column;
  height: 100vh;

  .scroll-container {
    padding: 0 40px 40px 40px;
    flex: 1;
    overflow-y: auto;
    overflow-x: hidden;
  }
}

@media (max-width: 650px) {
  .main-page {

    .scroll-container {
      padding: 0 10px 10px 10px;
    }
  }
}
</style>
