<template>
  <main class="v-fall-main v-fall-main--page-list">
    <div class="v-fall__container v-fall__container--white v-fall__container--list">
      <section class="v-fall-main-block grid grid-column">
        <h2 class="v-fall-main-block__header">Будущий тайтл</h2>
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
    }
  },
  methods: {
    openVideo(i) {
      this.$router.push(i);
    },
    // Исправить счетчик потом
    loadMore() {
      this.$axios
        .$get("https://api.videout.ru" + this.$route.fullPath + "&page=" + (+this.page)+1)
        .then(response => {
          this.videos = this.videos.concat(response.data);
          this.page = response.page
          console.log(this.page, 'page')
        });
    }
  },
  async asyncData({ $axios, params, route }) {
    const {data, page, page_count} = await $axios.$get("https://api.videout.ru/" + route.fullPath);

    return {
      videos: data,
      page, 
      page_count
    }
  },
  watch: {
    async $route() {
      console.log("change");
      const { data, page } = await this.$axios.$get(
        "https://api.videout.ru" + this.$route.fullPath
      );

      this.videos = data
      this.page = page
      console.log(this.page, 'page')
    }
  }
};
</script>