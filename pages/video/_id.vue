<template>
  <main class="v-fall-main">
    <div class="v-fall__container grid grid-column v-fall__container--inner">
      <section class="v-fall__container--white v-fall-inner__block" v-if="video">
        <h2 class="v-fall-inner__header">{{video.title}}</h2>
        <h4 class="v-fall-inner__subheader">{{video.subtitle}}</h4>
        <div
          class="v-fall-inner__video ut-overroll"
          style="width: 939px"
          v-html="video.player_code"
        ></div>
      </section>
      <section class="v-fall-inner__block v-fall-inner__block-poster" v-if="video">
        <div class="v-fall-inner__content">
          <div class="v-fall-inner__content-poster">
            <img class="v-fall-inner__content-img" style="width: 235px" :src="video.image" />
          </div>
          <div class="v-fall-inner__content-description grid grid-column">
            <div class="v-fall-inner__content-list">
              <div class="v-fall-inner__content-item">
                <span>Год</span>
                <span>{{video.year}}</span>
              </div>
              <div class="v-fall-inner__content-item">
                <span>Страна</span>
                <span>{{video.country}}</span>
              </div>
              <div class="v-fall-inner__content-item">
                <span>Жанр</span>
                <span>{{video.category}}</span>
              </div>
            </div>
            <span class="v-fall-inner__content-text">{{video.description}}</span>
          </div>
        </div>
      </section>
      <section class="v-fall__container--white v-fall-main-block v-fall-inner__block-container">
        <h2 class="v-fall-main-block__header">Новости</h2>
        <div class="v-fall-main-block__container" v-if="news">
          <a
            @click.prevent="openNews(item.url)"
            v-for="item in news"
            :key="item.id"
            class="v-fall-main-block__item v-fall-main-block__item--lg"
            href="#"
          >
            <img class="v-fall-main-block__img" style="width: 294px" :src="item.image" alt />
            <p class="v-fall-main-block__text">{{item.title}}</p>
          </a>
        </div>
      </section>
      <section class="v-fall__container--white v-fall-inner__block-container">
        <div class="v-fall-main-block v-fall-main-block__carousel">
          <h2 class="v-fall-main-block__header">Рекумондуем посмотреть</h2>
          <carousel
            v-if="isNuxtReady"
            :items="4"
            :loop="true"
            :margin="26"
            :autoWidth="true"
            :nav="false"
            :dots="false"
            class="v-fall-main-block__container v-fall-main-block__container-carousel"
          >
            <button slot="prev" class="v-fall-main-block__carousel-left"></button>
            <a
              @click.prevent="openVideo(item.url)"
              v-for="item in recommendations"
              :key="item.id"
              class="v-fall-main-block__item v-fall-main-block__item--lg"
              href="#"
            >
              <img class="v-fall-main-block__img" :src="item.image" alt />
              <h3 class="v-fall-main-block__title">{{item.title}}</h3>
              <p class="v-fall-main-block__content">
                <span class="v-fall-main-block__elem">{{item.year}}</span>
                <span class="v-fall-main-block__elem">{{item.category[0]}}</span>
              </p>
            </a>
            <button slot="next" class="v-fall-main-block__carousel-right"></button>
          </carousel>
        </div>
      </section>
    </div>
  </main>
</template>

<script>
const carousel = () =>
  window && window !== undefined ? import("v-owl-carousel") : null;
export default {
  components: {
    carousel
  },
  validate({ params }) {
    return /^\d+$/.test(params.id);
  },
  data: () => {
    return {
      video: null,
      news: null,
      recommendations: null,
      isNuxtReady: false
    };
  },
  methods: {
    openNews(i) {
      this.$router.push(i);
    }
  },
  mounted() {
    const vm = this;
    if (process.browser) {
      window.onNuxtReady(app => {
        vm.isNuxtReady = true;
      });
    }
  },
  async asyncData({ $axios, params, route }) {
    const { video, news, recommendations } = await $axios.$get(
      "https://api.videout.ru" + route.fullPath
    );
    console.log(video, 'vid')
    return {
      video,
      news,
      recommendations
    };
  }
};
</script>

<style lang="scss">
.v-fall-inner__block-container {
  padding-top: 40px;
}
</style>