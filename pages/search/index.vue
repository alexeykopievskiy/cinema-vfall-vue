<template>
  <main class="v-fall-main v-fall-main--page-list">
    <div class="v-fall__container v-fall__container--white v-fall__container--list">
      <section class="v-fall-main-block grid grid-column">
        <h2
          v-if="path == '/search/?genre=0&year=2019&country=0&sorting=rate'"
          class="v-fall-main-block__header"
        >Новинки</h2>
        <h2 v-if="path == '/search/'" class="v-fall-main-block__header">Фильмы</h2>
        <h2 v-if="path == '/search/?genre=73'" class="v-fall-main-block__header">Мультфильмы</h2>
        <div class="v-fall-main-block__container grid grid-wrap" v-if="videos">
          <a
            @click.prevent="openVideo(video.url)"
            v-for="video in videos"
            :key="video.id"
            class="v-fall-main-block__item"
            href="#"
          >
            <img class="v-fall-main-block__img" :src="video.image" alt />
            <h3 class="v-fall-main-block__title">{{video.title}}</h3>
            <p class="v-fall-main-block__content">
              <span class="v-fall-main-block__elem">{{video.year}}</span>
              <span class="v-fall-main-block__elem">{{video.category[0]}}</span>
            </p>
          </a>
        </div>
        <button
          class="v-fall-main-block__btn btn btn-default"
          @click="loadMore()"
          type="button"
        >Загрузить еще</button>
      </section>
    </div>
  </main>
</template>

<script>
export default {
  data: () => {
    return {
      videos: null,
      path: null
    };
  },
  methods: {
    openVideo(i) {
      this.$router.push(i);
    },
    // Исправить счетчик потом
    loadMore() {
      this.$axios
      .$get("https://api.videout.ru" + this.$route.fullPath + '&page=2')
      .then(response => {
        this.videos = this.videos.concat(response.data);
      });
    }
  },
  mounted() {
    this.$axios
      .$get("https://api.videout.ru" + this.$route.fullPath)
      .then(response => {
        this.videos = response.data;
      });
  },
  watch: {
    $route() {
      this.$axios
        .$get("https://api.videout.ru" + this.$route.fullPath)
        .then(response => {
          this.path = this.$route.fullPath;
          this.videos = response.data;
        });
    }
  }
};
</script>