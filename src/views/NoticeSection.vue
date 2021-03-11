<template>
  <section class="notice">
    <div class="notice-line">
      <div class="bg-left" />
      <div class="bg-right" />
      <div class="inner">
        <div class="inner__left">
          <h2>공지사항</h2>
          <swiper
            :direction="'vertical'"
            :autoplay="true"
            :loop="true"
            @swiper="onSwiper"
            @slideChange="onSlideChange"
          >
            <swiper-slide>
              <a href="javascript:void(0)">
                크리스마스 & 연말연시 스타벅스 매장 영엽시간 변경 안내
              </a>
            </swiper-slide>
            <swiper-slide>
              <a href="javascript:void(0)">
                [당첨자 발표] 2021 스타벅스 플래너 영수증 이벤트
              </a>
            </swiper-slide>
            <swiper-slide>
              <a href="javascript:void(0)">
                스타벅스커피 코리아 애플리케이션 버전 업데이트 안내
              </a>
            </swiper-slide>
            <swiper-slide>
              <a href="javascript:void(0)">
                [당첨자 발표] 뉴이어 전자영수증 이벤트
              </a>
            </swiper-slide>
          </swiper>
          <a
            href="javascript:void(0)"
            class="notice-line__more"
          >
            <div class="material-icons">
              add_circle
            </div>
          </a>
        </div>
        <div class="inner__right">
          <h2>스타벅스 프로모션</h2>
          <div class="toggle-promotion">
            <div class="material-icons">
              upload
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="promotion">
      <swiper
        :slides-per-view="3"
        :loop="true"
        :space-between="10"
        :centered-slides="true"
        :pagination="{ clickable: true }"
        navigation
      >
        <swiper-slide>
          <img
            src="@/assets/images/promotion_slide1.jpg"
            alt="2021 뉴이어, 스타벅스와 함께 즐겁고 활기차게 시작하세요!"
          >
          <a
            href="javascript:void(0)"
            class="btn"
          >
            자세히 보기
          </a>
        </swiper-slide>
        <swiper-slide>
          <img
            src="@/assets/images/promotion_slide2.jpg"
            alt="기간 내 스타벅스 카드 e-Gift를 3만원 이상 선물 시, 아메리카노 e-쿠폰을 드립니다."
          >
          <a
            href="javascript:void(0)"
            class="btn"
          >
            자세히 보기
          </a>
        </swiper-slide>
        <swiper-slide>
          <img
            src="@/assets/images/promotion_slide3.jpg"
            alt="2021 뉴이어, 스타벅스와 함께 즐겁고 활기차게 시작하세요!"
          >
          <a
            href="javascript:void(0)"
            class="btn"
          >
            자세히 보기
          </a>
        </swiper-slide>
        <swiper-slide>
          <img
            src="@/assets/images/promotion_slide4.jpg"
            alt="2021 뉴이어, 스타벅스와 함께 즐겁고 활기차게 시작하세요!"
          >
          <a
            href="javascript:void(0)"
            class="btn"
          >
            자세히 보기
          </a>
        </swiper-slide>
        <swiper-slide>
          <img
            src="@/assets/images/promotion_slide5.jpg"
            alt="2021 뉴이어, 스타벅스와 함께 즐겁고 활기차게 시작하세요!"
          >
          <a
            href="javascript:void(0)"
            class="btn"
          >
            자세히 보기
          </a>
        </swiper-slide>
      </swiper>
    </div>
  </section>
</template>

<script>  
// import Swiper core and required modules
import SwiperCore, { Navigation, Pagination, Scrollbar, A11y, Autoplay } from 'swiper';

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';

// Import Swiper styles
import 'swiper/swiper.scss';
import 'swiper/components/navigation/navigation.scss';
import 'swiper/components/pagination/pagination.scss';
import 'swiper/components/scrollbar/scrollbar.scss';

// install Swiper modules
SwiperCore.use([Navigation, Pagination, Scrollbar, A11y, Autoplay]);


export default {
  name: "NoticeSection",
  components: {
    Swiper,
    SwiperSlide,
  },
  mounted() {
    const buttonPrev = document.createElement('div');
    buttonPrev.className = "material-icons"
    const buttonNext = document.createElement('div');
    buttonNext.className = "material-icons"

    const buttonTextPrev = document.createTextNode('arrow_back');
    const buttonTextNext = document.createTextNode('arrow_forward');
    buttonPrev.appendChild(buttonTextPrev);
    buttonNext.appendChild(buttonTextNext);

    document.getElementsByClassName("swiper-button-prev")[0].appendChild(buttonPrev);
    document.getElementsByClassName("swiper-button-next")[0].appendChild(buttonNext);



    // let insertElement = document.getElementsByClassName("swiper-button-prev");
    // console.log(insertElement);
    // console.log(insertElement.childNodes[0]);
    // insertElement.insertBefore(buttonPrev, insertElement);



  },
  methods: {
    prev() {
      this.$refs.swiper.$el.slideNext()
    },
    next() {
      this.$refs.swiper.$el.slideNext()
    }
  },
  date() {
    return {
    }
  }
}
</script>

<style>

</style>