<template>
  <main class="v-fall-main">
    <div
      class="v-fall__container v-fall__container--white v-fall__container--main"
      style="padding-top: 10px; margin-top: 10px;"
    >
      <section class="v-fall-main-block">
        <h2 class="v-fall-main-block__header">Фильмы</h2>
        <div class="v-fall-main-block__container" v-if="films">
          <a
            @click.prevent="openVideo(item.url)"
            v-for="item in films.slice(0, 6)"
            :key="item.id"
            class="v-fall-main-block__item"
            href="#"
          >
            <img class="v-fall-main-block__img" :src="item.image" alt />
            <h3 class="v-fall-main-block__title">{{item.title}}</h3>
            <p class="v-fall-main-block__content">
              <span class="v-fall-main-block__elem">{{item.year}}</span>
              <span class="v-fall-main-block__elem">{{item.category[0]}}</span>
            </p>
          </a>
        </div>
      </section>
      <section class="v-fall-main-block v-fall-main-block__carousel">
        <h2 class="v-fall-main-block__header">РЕКОМЕНДУЕМ ПОСМОТРЕТЬ</h2>
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
            @click.prevent="openVideo(i)"
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
      </section>
      <section class="v-fall-main-block">
        <h2 class="v-fall-main-block__header">Мультфильмы</h2>
        <p class="v-fall-main-block__subtitle">Коллекция лучших мультфильмов для детей и родителей</p>
        <div class="v-fall-main-block__container" v-if="cartoons">
          <a
            @click.prevent="openVideo(item.url)"
            v-for="item in cartoons.slice(0, 6)"
            :key="item.id"
            class="v-fall-main-block__item"
            href="#"
          >
            <img class="v-fall-main-block__img" :src="item.image" alt />
            <h3 class="v-fall-main-block__title">{{item.title}}</h3>
            <p class="v-fall-main-block__content">
              <span class="v-fall-main-block__elem">{{item.year}}</span>
              <span class="v-fall-main-block__elem">{{item.category}}</span>
            </p>
          </a>
        </div>
      </section>
      <section class="v-fall-main-block">
        <h2 class="v-fall-main-block__header">Новости</h2>
        <p class="v-fall-main-block__subtitle">Коллекция лучших мультфильмов для детей и родителей</p>
        <div class="v-fall-main-block__container" v-if="news">
          <a
            @click.prevent="openNews(item.url)"
            v-for="item of news.slice(0, 4)"
            :key="item.id"
            class="v-fall-main-block__item v-fall-main-block__item--lg"
            href="#"
          >
            <img class="v-fall-main-block__img" :src="item.image" alt />
            <p class="v-fall-main-block__text">{{item.title}}</p>
          </a>
        </div>
      </section>
    </div>
  </main>
</template>

<script>
const carousel = () =>
  window && window !== undefined ? import("v-owl-carousel") : null;
let requestUrl = "https://api.videout.ru";
let requestNew =
  "https://api.videout.ru/search/?genre=0&year=2019&country=0&sorting=rate";
let requestFilms = "https://api.videout.ru/search/";
let requestCartoons = "https://api.videout.ru/search/?genre=73";
let requestNews = "https://api.videout.ru/news";

export default {
  components: {
    carousel
  },
  data: () => {
    return {
      source: null,
      hot: null,
      films: null,
      cartoons: null,
      news: null,
      isNuxtReady: false
    };
  },
  beforeCreate() {
    console.log("before create");
  },
  mounted() {
    const vm = this;
    //this.$nextTick(() => {
    //this.$nuxt.$loading.start();
    //});

    if (process.browser) {
      window.onNuxtReady(app => {
        console.log("Nuxt ready!");
        vm.isNuxtReady = true;
      });
    }
  },
  methods: {
    openVideo(i) {
      this.$router.push(i);
    },
    openNews(i) {
      this.$router.push(i);
    }
  },
  async asyncData({ $axios, params }) {
    let response = await $axios.get(requestUrl);
    let responseNews = await $axios.get(requestNews);
    console.log(response, "res");
    return {
      recommendations: response.data.recommendations,
      films: response.data.movies,
      cartoons: response.data.cartoons,
      news: responseNews.data.data
    };
  }
};
</script>

<style lang="scss">
.v-fall-main {
  &-slide {
    &__prev {
      margin-left: 80px;
      background: transparent url("../assets/img/arrow.png") no-repeat;
      width: 27px;
      height: 42px;
      border: none;
      outline: none;
      cursor: pointer;

      &:hover {
        background: transparent url("../assets/img/arrow-hover.png") no-repeat;
        transform: rotate(-180deg);
      }
    }
    &__next {
      margin-right: 80px;
      margin-left: 80px;
      background: transparent url("../assets/img/arrow.png") no-repeat;
      width: 27px;
      height: 42px;
      border: none;
      outline: none;
      transform: rotate(-180deg);
      cursor: pointer;

      &:hover {
        background: transparent url("../assets/img/arrow-hover.png") no-repeat;
        transform: rotate(0deg);
      }
    }
  }
  &-block {
    &__carousel {
      &-left {
        background: transparent url("../assets/img/arrow-hover.png") no-repeat;
        width: 27px;
        height: 42px;
        margin-left: 24px;
        transform: rotate(-180deg);
        border: none;
        outline: none;
        cursor: pointer;
        position: relative;
        z-index: 100;
      }
      &-right {
        background: transparent url("../assets/img/arrow-hover.png") no-repeat;
        width: 27px;
        height: 42px;
        margin-right: 24px;
        border: none;
        outline: none;
        cursor: pointer;
        position: relative;
        z-index: 100;
      }
    }
  }
}
.v-fall-main-block__container-carousel > span {
  position: absolute;
  top: 50%;
  left: 0;
}

.owl-carousel.owl-theme + span {
  left: initial;
  right: 0;
}

.owl-carousel.owl-loaded {
  display: flex !important;
}

.v-fall-main-block__img {
  width: 100%;
  height: auto;
}
</style>
