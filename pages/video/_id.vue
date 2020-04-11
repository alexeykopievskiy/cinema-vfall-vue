<template>
  <main class="v-fall-main">
    <div class="v-fall__container grid grid-column v-fall__container--inner">
      <section class="v-fall__container--white v-fall-inner__block">
        <h2 class="v-fall-inner__header">Фаворитка</h2>
        <h4 class="v-fall-inner__subheader">The Favourite</h4>
        <div class="v-fall-inner__video">
          <video
            width="939"
            poster="https://html5book.ru/examples/media/white_cherry_tree.jpg"
            loop
          >
            <source
              src="https://html5book.ru/examples/media/blossoming_white_cherry_tree.mp4"
              type="video/mp4"
            />
          </video>
          <div class="v-fall-inner__video-mask">
            <button class="v-fall-inner__video-btn"></button>
          </div>
        </div>
      </section>
      <section class="v-fall-inner__block v-fall-inner__block-poster">
        <div class="v-fall-inner__content">
          <div class="v-fall-inner__content-poster">
            <img class="v-fall-inner__content-img" src="~assets/img/inner.jpg" />
          </div>
          <div class="v-fall-inner__content-description grid grid-column">
            <div class="v-fall-inner__content-list">
              <div class="v-fall-inner__content-item">
                <span>Год</span>
                <span>2015</span>
              </div>
              <div class="v-fall-inner__content-item">
                <span>Страна</span>
                <span>Англия</span>
              </div>
              <div class="v-fall-inner__content-item">
                <span>Жанр</span>
                <span>Комедия</span>
              </div>
            </div>
            <span
              class="v-fall-inner__content-text"
            >Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est eopksio laborum. Sed ut perspiciatis unde omnis istpoe natus error sit voluptatem accusantium doloremque eopsloi laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunot explicabo. Nemo ernim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sedopk quia consequuntur magni dolores eos qui rationesopl voluptatem sequi nesciunt. Neque porro quisquameo est, qui dolorem ipsum quia dolor sit amet, eopsmiep consectetur, adipisci velit, seisud quia non numquam eius modi tempora incidunt ut labore et dolore wopeir magnam aliquam quaerat voluptatem eoplmuriquisqu</span>
            <span class="v-fall-inner__content-slide">Развернуть</span>
          </div>
        </div>
      </section>
      <section class="v-fall__container--white v-fall-main-block v-fall-inner__block-container">
        <h2 class="v-fall-main-block__header">Новости</h2>
        <div class="v-fall-main-block__container">
          <a class="v-fall-main-block__item v-fall-main-block__item--lg" href="#">
            <img class="v-fall-main-block__img" src="~assets/img/img5.jpg" alt />
            <p
              class="v-fall-main-block__text"
            >Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id</p>
          </a>
          <a class="v-fall-main-block__item v-fall-main-block__item--lg" href="#">
            <img class="v-fall-main-block__img" src="~assets/img/img6.jpg" alt />
            <p
              class="v-fall-main-block__text"
            >Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id</p>
          </a>
          <a class="v-fall-main-block__item v-fall-main-block__item--lg" href="#">
            <img class="v-fall-main-block__img" src="~assets/img/img7.jpg" alt />
            <p
              class="v-fall-main-block__text"
            >Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id</p>
          </a>
          <a class="v-fall-main-block__item v-fall-main-block__item--lg" href="#">
            <img class="v-fall-main-block__img" src="~assets/img/img8.jpg" alt />
            <p
              class="v-fall-main-block__text"
            >Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id</p>
          </a>
        </div>
      </section>
      <section class="v-fall__container--white v-fall-inner__block-container">
        <div class="v-fall-main-block v-fall-main-block__carousel">
          <h2 class="v-fall-main-block__header">Planeta online</h2>
          <div
            class="v-fall-main-block__container v-fall-main-block__container-carousel owl-carousel"
          >
            <a class="v-fall-main-block__item v-fall-main-block__item--lg" href="#">
              <img class="v-fall-main-block__img" src="~assets/img/img5.jpg" alt />
              <h3 class="v-fall-main-block__title">Фаворитка</h3>
              <p class="v-fall-main-block__content">
                <span class="v-fall-main-block__elem">2011</span>
                <span class="v-fall-main-block__elem">Мелодрамма</span>
              </p>
            </a>
            <a class="v-fall-main-block__item v-fall-main-block__item--lg" href="#">
              <img class="v-fall-main-block__img" src="~assets/img/img6.jpg" alt />
              <h3 class="v-fall-main-block__title">Стекло</h3>
              <p class="v-fall-main-block__content">
                <span class="v-fall-main-block__elem">2019</span>
                <span class="v-fall-main-block__elem">Боевик</span>
              </p>
            </a>
            <a class="v-fall-main-block__item v-fall-main-block__item--lg" href="#">
              <img class="v-fall-main-block__img" src="~assets/img/img7.jpg" alt />
              <h3 class="v-fall-main-block__title">Море соблазна</h3>
              <p class="v-fall-main-block__content">
                <span class="v-fall-main-block__elem">2019</span>
                <span class="v-fall-main-block__elem">Боевик</span>
              </p>
            </a>
            <a class="v-fall-main-block__item v-fall-main-block__item--lg" href="#">
              <img class="v-fall-main-block__img" src="~assets/img/img8.jpg" alt />
              <h3 class="v-fall-main-block__title">Фаворитка</h3>
              <p class="v-fall-main-block__content">
                <span class="v-fall-main-block__elem">2011</span>
                <span class="v-fall-main-block__elem">Мелодрамма</span>
              </p>
            </a>
          </div>
          <div class="v-fall-main-block__carousel-btn">
            <button class="v-fall-main-block__carousel-left"></button>
            <button class="v-fall-main-block__carousel-right"></button>
          </div>
        </div>
      </section>
    </div>
  </main>
</template>

<script>
export default {
  validate({ params }) {
    return /^\d+$/.test(params.id);
  }
};
</script>