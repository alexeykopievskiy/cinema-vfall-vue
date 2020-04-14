<template>
  <main class="v-fall-main v-fall-main--page-list">
    <div class="v-fall__container v-fall__container--white v-fall__container--list">
      <section class="v-fall-main-block grid grid-column">
        <h2 class="v-fall-main-block__header">{{title}}</h2>
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
          v-if="loadBtn"
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
      loadBtn: true,
      videos: null,
      page: null,
      page_count: null
    };
  },
  methods: {
    openVideo(i) {
      this.$router.push(i);
    },
    async loadMore() {
      if (this.page != this.page_count) {
        const { data, page } = await this.$axios.$get(
          "https://api.videout.ru" +
            this.$route.fullPath +
            "&limit=24&page=" +
            ++this.page
        );

        if (this.page_count == page) this.loadBtn = false;
        this.videos = this.videos.concat(data);

        return {
          page
        };
      }
    }
  },
  async asyncData({ $axios, params, route }) {
    const { data, page, page_count, title } = await $axios.$get(
      "https://api.videout.ru/" + route.fullPath
    );
    if (page_count == 1) this.loadBtn = false;
    return {
      videos: data,
      page,
      page_count,
      title
    };
  },
  watch: {
    async $route() {
      const { data, page, title, page_count } = await this.$axios.$get(
        "https://api.videout.ru" + this.$route.fullPath
      );
      this.videos = data;

      return {
        page,
        page_count
      };
    }
  }
};
</script>