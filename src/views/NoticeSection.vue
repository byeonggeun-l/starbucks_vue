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
  },
  methods: {
    onSwiper(swiper) {
    },
    onSlideChange() {
    },
  },
}
</script>

<style>

</style>