<template>
  <section class="visual">
    <div class="inner">
      <div class="title">
        <FadeElement 
          :el-tag-name="'img'"
          :img-tag-src="'images/visual_title.png'"
          :img-tag-alt="'STARBUCKS DELIGHTFUL START TO THE YEARS'"
          :fade-sec="1"
        />
        <FadeElement 
          :el-tag-name="'a'"
          :class-list="'btn btn--brown'"
          :a-tag-inner-text="'자세히 보기'"
          :fade-sec="1"
        />
      </div>
      <div>
        <FadeElement 
          :el-tag-name="'img'"
          :class-list="'cup1 image'"
          :img-tag-src="'images/visual_cup1.png'"
          :img-tag-alt="'NEW OATMEAL LATTE'"
          :fade-sec="2"
        />
        <FadeElement 
          :el-tag-name="'img'"
          :class-list="'cup1 text'"
          :img-tag-src="'images/visual_cup1_text.png'"
          :img-tag-alt="'오트밀 라떼'"
          :fade-sec="2"
        />
      </div>
      <div>
        <FadeElement 
          :el-tag-name="'img'"
          :class-list="'cup2 image'"
          :img-tag-src="'images/visual_cup2.png'"
          :img-tag-alt="'NEW STARBUCKS CARAMEL CRUMBLE MOCHA'"
          :fade-sec="3"
        />
        <FadeElement 
          :el-tag-name="'img'"
          :class-list="'cup2 text'"
          :img-tag-src="'images/visual_cup2_text.png'"
          :img-tag-alt="'스타벅스 카라멜 크럼블 모카'"
          :fade-sec="3"
        />
      </div>
      <div>
        <FadeElement
          :el-tag-name="'img'"
          :class-list="'spoon'"
          :img-tag-src="'images/visual_spoon.png'"
          :img-tag-alt="'Spoon'"
          :fade-sec="4"
        />
      </div>
    </div>
  </section>
</template>

<script>
import FadeElement from '@/components/FadeElement.vue'
import gsap from "gsap";

export default {
  name: "VisualSection",
  components:{
    FadeElement,
  },
  mounted() {
    // const fadeEls = document.querySelectorAll('.visual .fade-in');
    // fadeEls.forEach(function (fadeEl, index) {
    //   gsap.to(fadeEl, 1, 
    //     {
    //       delay: (index + 1) *  .7,
    //       opacity : 1
    //     }
    //   );
    // })
  }
}
</script>

<style>
.visual {
    margin-top: 120px;
    background-position: center;
    background-image: url("../assets/images/visual_bg.jpg");
}
</style>