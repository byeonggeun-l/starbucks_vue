<template>
  <section class="visual">
    <div class="inner">
      <div class="title">
        <img
          src="@/assets/images/visual_title.png"
          alt="STARBUCKS DELIGHTFUL START TO THE YEARS"
        >
        <a
          href="javascript:void(0)"
          class="btn btn--brown"
        >
          자세히 보기
        </a> 
      </div>
      <img
        src="@/assets/images/visual_cup1.png"
        alt="NEW OATMEAL LATTE"
        class="cup1 image"
      >
      <img
        src="@/assets/images/visual_cup1_text.png"
        alt="오트밀 라떼"
        class="cup1 text"
      >
      <img
        src="@/assets/images/visual_cup2.png"
        alt="NEW STARBUCKS CARAMEL CRUMBLE MOCHA"
        class="cup2 image"
      >
      <img
        src="@/assets/images/visual_cup2_text.png"
        alt="스타벅스 카라멜 크럼블 모카"
        class="cup2 text"
      >
      <img
        src="@/assets/images/visual_spoon.png"
        alt="Spoon"
        class="spoon"
      >
    </div>
  </section>
</template>

<script>
export default {
  name: "VisualSection",
}
</script>

<style>
.visual {
    margin-top: 120px;
    background-position: center;
    background-image: url("../assets/images/visual_bg.jpg");
}
</style>