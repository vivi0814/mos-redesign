<template>
  <div class="body">
    <div class="banner">
      <swiper
        :navigation="{
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        }"
        :modules="modules"
        :autoplay="autoplay"
        :loop="true"
        class="mySwiper"
      >
        <button class="swiper-button-next"></button>
        <button class="swiper-button-prev"></button>
        <swiper-slide
          v-for="(slide, index) in slides"
          :key="index"
          class="banner-item"
        >
          <img :src="slide.image" :alt="slide.image" loading="lazy" />
        </swiper-slide>
      </swiper>
    </div>
    <div class="burger">
      <span class="burger-block"></span>
      <swiper
        :slidesPerView="1"
        :breakpoints="breakpoints"
        :autoplay="autoplay"
        :loop="true"
        :navigation="{
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        }"
        :modules="modules"
        class="mySwiper"
      >
        <button class="swiper-button-prev"></button>
        <button class="swiper-button-next"></button>

        <swiper-slide
          v-for="(item, index) in BurgerItems"
          :key="index"
          class="burger-item"
        >
          <a href="#">
            <div class="burger-item-pic">
              <img :src="item.image" :alt="item.title" loading="lazy" />
            </div>
            <p class="burger-title">{{ item.title }}</p>
          </a>
        </swiper-slide>
      </swiper>
    </div>
    <main class="content">
      <div class="content-news">
        <div v-for="(item, index) in NewsItems" :key="index" class="news-item">
          <a href="#">
            <div class="news-item-pic">
              <img :src="item.image" :alt="item.image" loading="lazy" />
              <p class="more fontSize16-15em">
                more
                <span class="material-symbols-outlined"> arrow_right_alt </span>
              </p>
            </div>
          </a>
        </div>
      </div>
      <div class="content-block">
        <div
          v-for="(item, index) in BlocksItems"
          :key="index"
          class="blocks-item"
        >
          <a href="#">
            <div class="blocks-item-pic">
              <img :src="item.image" :alt="item.image" />
              <p class="more fontSize16-15em">
                more
                <span class="material-symbols-outlined"> arrow_right_alt </span>
              </p>
            </div>
          </a>
        </div>
        <div class="blocks-item-social">
          <div
            v-for="(item, index) in BlocksItemsSocial"
            :key="index"
            class="blocks-item-social-pic"
          >
            <a href="#">
              <img :src="item.image" :alt="item.image" />
            </a>
          </div>
        </div>
      </div>
      <div class="content-intro">
        <div class="intro-txt-img">
          <p class="intro-txt fontSize16-15em">
            熟悉的味道、像家人般用心是為了給您「最美味的溫度與鮮度」<br />
            人生就像一場旅行，旅途中有願意陪伴您一起的好夥伴，就是「幸福的滋味」
          </p>
          <div class="intro-img">
            <img src="/assets/img/image 28.png" alt="image" loading="lazy" />
          </div>
        </div>
        <span class="intro-block"></span>
        <div class="video-container">
          <iframe
            :src="youtubeUrl"
            title="YouTube video player"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
          ></iframe>
        </div>
        <div class="intro-img2"></div>
      </div>
    </main>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/pagination";
import "swiper/css/navigation";
import { Navigation, Autoplay } from "swiper/modules";

const modules = [Navigation, Autoplay];

const slides = ref([
  { image: "/assets/img/mos-banner.jpg" },
  { image: "/assets/img/mos-banner-2.jpg" },
  { image: "/assets/img/mos-banner-3.jpg" },
  { image: "/assets/img/mos-banner-4.jpg" },
]);

const BurgerItems = ref([
  { image: "/assets/img/burger.svg", title: "照燒青梅豬排堡" },
  { image: "/assets/img/burger2.svg", title: "北海道起司牛肉堡" },
  { image: "/assets/img/burger3.svg", title: "元氣魔力珍珠堡" },
  { image: "/assets/img/burger4.svg", title: "和風舒活牛肉堡" },
  { image: "/assets/img/burger5.svg", title: "元氣牛肉珍珠堡" },
  { image: "/assets/img/burger6.svg", title: "摘鮮綠摩斯炸蝦堡" },
  { image: "/assets/img/burger7.svg", title: "海洋珍珠大麥堡" },
  { image: "/assets/img/burger4.svg", title: "和風舒活牛肉堡" },
  { image: "/assets/img/burger2.svg", title: "北海道起司牛肉堡" },
]);
const breakpoints = {
  400: { slidesPerView: 2 },
  600: { slidesPerView: 3 },
  768: { slidesPerView: 4 },
  900: { slidesPerView: 5 },
  1200: { slidesPerView: 6 },
  1500: { slidesPerView: 7 },
};
const autoplay = {
  delay: 2500,
  disableOnInteraction: false,
};
const NewsItems = ref([
  { image: "/assets/img/new1.png" },
  { image: "/assets/img/new2.png" },
]);
const BlocksItems = ref([
  { image: "/assets/img/Group 158.png" },
  { image: "/assets/img/Group 159.png" },
  { image: "/assets/img/Group 27.png" },
  { image: "/assets/img/Group 28.png" },
  { image: "/assets/img/image 57.png" },
  { image: "/assets/img/image 58.png" },
  { image: "/assets/img/image 59.png" },
]);
const BlocksItemsSocial = [
  { image: "/assets/img/Group 223.png" },
  { image: "/assets/img/Group 36.png" },
];
const youtubeUrl = ref(
  "https://www.youtube.com/embed/n8cZxqIH6kM?autoplay=1&loop=1&playlist=n8cZxqIH6kM&mute=1&controls=0&rel=0&modestbranding=1"
);
</script>

<style lang="scss" scoped>
@import "../assets/scss/color.scss";

.body {
  position: relative;
  overflow-x: hidden;
}
.banner {
  .swiper {
    .swiper-button-next,
    .swiper-button-prev {
      background-color: #fff;
      color: $text_color_main;
      border-radius: 50%;
      border: none;
      width: 40px;
      height: 40px;
    }
    .swiper-button-next::after,
    .swiper-button-prev::after {
      font-size: 12px;
    }
    .swiper-slide img {
      display: block;
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
}
.burger {
  position: relative;
  .burger-block {
    position: absolute;
    top: 3rem;
    display: block;
    height: 17rem;
    width: 80vw;
    z-index: -100;
    background-color: rgba(214, 148, 78, 0.161);
    border-radius: 0 30px 30px 0;
  }
  &-item {
    text-align: center;
    width: 100%;

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 325px;

    > a {
      text-decoration: none;

      &:hover > .burger-item-pic img {
        transform: scale(1.1);
      }
    }
  }
  &-title {
    color: $text_color_main;
    text-shadow: 2px 2px 4px #ffffff;
    margin-bottom: 0;
  }
  &-item-pic {
    padding: 10px;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 150px;
    height: 150px;
    margin: 10px auto;
    background-color: #fff;
    border-radius: 50%;
    overflow: hidden;

    > img {
      transition: 0.5s;
      max-width: 100%;
      max-height: 100%;
      object-fit: cover;
    }
  }
  .swiper .swiper-button-next,
  .swiper .swiper-button-prev {
    text-indent: 180%;
    white-space: nowrap;
    overflow: hidden;
    border: none;
  }
  .swiper .swiper-button-next {
    background: url("/assets/img/arrow-right.png") no-repeat center;
  }
  .swiper .swiper-button-prev {
    background: url("/assets/img/arrow-left.png") no-repeat center;
  }
}
.content {
  max-width: 960px;
  margin: auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  .content-news,
  .content-block {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
  }
  .news-item {
    width: 95%;
    margin-top: 20px;
    transition: transform 0.3s;
    &:hover {
      transform: translateY(-5px);
    }
    > a {
      text-decoration: none;
    }
    .news-item-pic {
      position: relative;
      margin: auto;
      img {
        width: 100%;
      }
      .more {
        position: absolute;
        right: -1px;
        bottom: 0;
        padding: 2px 7px;
        display: flex;
        align-items: center;
        color: #000;
        background-color: $bcg_color;
        border-radius: 10px 0 10px 0;
      }
    }
  }
  .blocks-item {
    width: calc(50% - 20px);
    margin-top: 20px;
    transition: transform 0.3s;
    &:hover {
      transform: translateY(-5px);
    }
    > a {
      text-decoration: none;
    }
    .blocks-item-pic {
      width: 100%;
      position: relative;
      img {
        width: 100%;
      }
      .more {
        position: absolute;
        right: -1px;
        bottom: 0;
        padding: 2px 7px;
        display: flex;
        align-items: center;
        color: #000;
        background-color: $bcg_color;
        border-radius: 10px 0 10px 0;
      }
    }
  }
  .blocks-item-social {
    width: calc(50% - 20px);
    margin-top: 20px;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;

    .blocks-item-social-pic {
      transition: transform 0.3s;
      &:hover {
        transform: translateY(-5px);
      }
      > a {
        text-decoration: none;
      }
      width: 100%;
      img {
        width: 100%;
      }
    }
  }
  .content-intro {
    // margin: auto;

    // position: relative;
    .intro-txt-img {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      // justify-content: space-between;
      padding: 10px;
    }
    .intro-txt {
      // margin-top: 3rem;
      color: $text_color_main;
      width: 45%;
      min-width: 300px;
      // margin-right: 5rem;
    }
    .intro-img {
      margin-top: 10px;
      // margin-right: -2rem;
      width: 45%;
      min-width: 250px;
      height: 300px;
      // background: url("../src/assets/img/image 28.png") no-repeat center;
      animation: float 3s ease-in-out infinite;
      img {
        width: 95%;
      }
    }
    @keyframes float {
      0% {
        transform: translateY(0);
      }
      50% {
        transform: translateY(-10px);
      }
      100% {
        transform: translateY(0);
      }
    }
    .intro-img2 {
      margin-top: 10px;
      margin-left: -2rem;
      width: 350px;
      height: 300px;
      background: url("/assets/img/image 33.png") no-repeat center;
      animation: float 3s ease-in-out infinite;
    }
    .intro-block {
      position: absolute;
      display: block;
      width: 70vw;
      height: 23rem;
      z-index: -100;
      // top: 2px;
      bottom: 10rem;
      right: 0;
      border-radius: 30px 0 0 30px;
      background-color: #d6944e59;
    }
    .video-container {
      position: relative;
      margin: auto;
      width: 100%;
      max-width: 750px;
      padding-bottom: 43.75%; /* 16:9 比例 */
      height: 0;
      overflow: hidden;
      iframe {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        border-radius: 3px;
      }
    }
  }
}
@media (max-width: 767px) {
  .content {
    .content-intro {
      .intro-txt-img {
        justify-content: center;
      }
    }
  }
}
@media screen and (min-width: 768px) {
  .content {
    .news-item {
      width: calc(50% - 20px);
    }
    .blocks-item,
    .blocks-item-social {
      width: calc(25% - 20px);
    }

    .content-intro {
      .intro-txt-img {
        justify-content: space-around;
      }
    }
  }
}

</style>