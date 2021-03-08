<template>
  <!-- HEADER -->
  <header>
    <div class="inner">
      <a
        href="/"
        class="logo"
      >
        <img
          src="@/assets/images/starbucks_logo.png"
          alt="STARBUCKS"
        >
      </a>
      <div class="sub-menu">
        <ul class="menu">
          <li>
            <a href="/signin">
              Sign In
            </a>
          </li>
          <li>
            <a href="javascript:void(0)">
              My Starbucks
            </a>
          </li>
          <li>
            <a href="javascript:void(0)">
              Customer Service & Ideas
            </a>
          </li>
          <li>
            <a href="javascript:void(0)">
              Find a Store
            </a>
          </li>
        </ul>
        <div
          ref="refSearch"
          class="search"
          @click="clickSearch"
        >
          <input
            ref="refSearchInput"
            type="text"
            @blur="blurSearch"
          >
          <div
            class="material-icons"
          >
            search
          </div>
        </div>
      </div>

      <ul class="main-menu">
        <li class="item">
          <div class="item__name">
            COFFEE
          </div>
          <div class="item__contents">
            <div class="contents__menu">
              <ul class="inner">
                <li>
                  <h4>커피</h4>
                  <ul>
                    <li>스타벅스 원두</li>
                    <li>스타벅스 비아</li>
                    <li>스타벅스 오리가미</li>
                  </ul>
                </li>
                <li>
                  <h4>에스프레소 음료</h4>
                  <ul>
                    <li>도피오</li>
                    <li>에스프레소 마키아또</li>
                    <li>아메리카노</li>
                    <li>마키아또</li>
                    <li>카푸치노</li>
                    <li>라떼</li>
                    <li>모카</li>
                    <li>리스트레도 비안코</li>
                  </ul>
                </li>
              </ul>
            </div>
            <div class="contents__texture">
              <div class="inner">
                <h4>나와 어울리는 커피 찾기</h4>
                <p>스타벅스가 여러분에게 어울리는 커피를 찾아드립니다.</p>
                <h4>최상의 커피를 즐기는 법</h4>
                <p>여러가지 방법을 통해 다양한 풍미의 커피를 즐겨보세요.</p>
              </div>
            </div>
          </div>
        </li>
        <li class="item">
          <div class="item__name">
            MENU
          </div>
          <div class="item__contents">
            <div class="contents__menu">
              <div class="inner">
                MENU
              </div>
            </div>
            <div class="contents__texture">
              <div class="inner">
                MENU
              </div>
            </div>
          </div>
        </li>
        <li class="item">
          <div class="item__name">
            STORE
          </div>
          <div class="item__contents">
            <div class="contents__menu">
              contents__menu
            </div>
            <div class="contents__texture">
              contents__texture
            </div>
          </div>
        </li>
        <li class="item">
          <div class="item__name">
            RESPONSIBILITY
          </div>
          <div class="item__contents">
            <div class="contents__menu">
              contents__menu
            </div>
            <div class="contents__texture">
              contents__texture
            </div>
          </div>
        </li>
        <li class="item">
          <div class="item__name">
            MY STARBUCKS REWARDS
          </div>
          <div class="item__contents">
            <div class="contents__menu">
              contents__menu
            </div>
            <div class="contents__texture">
              contents__texture
            </div>
          </div>
        </li>
        <li class="item">
          <div class="item__name">
            WHAT'S NEW
          </div>
          <div class="item__contents">
            <div class="contents__menu">
              contents__menu
            </div>
            <div class="contents__texture">
              contents__texture
            </div>
          </div>
        </li>
      </ul>
    </div>
  </header>
</template>

<script>



export default {
  mounted() {

  },
  
  methods: {
  },
  methods:{
    clickSearch(e) {
      this.$refs.refSearchInput.focus();
      this.$refs.refSearch.classList.add('focused');
      this.$refs.refSearchInput.setAttribute('placeholder', '통합검색');
    },
    blurSearch(e) {
      this.$refs.refSearch.classList.remove('focused');
      this.$refs.refSearchInput.setAttribute('placeholder', '');
    }
  }
}
</script>

<style scoped lang="scss">
header {
  background-color: #f6f5f0;
  border-bottom: 1px solid #c8c8c8;
}
header > .inner {
  height: 120px;
}
header .logo {
  height:75px;
  /* position:absolute;
  부모(static 속성이 아닌) 또는 body
  기준으로 움직인다. */
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  margin: auto;
}
header .sub-menu {
  position:absolute;
  top: 10px;
  right: 0;
  display:flex;
}
header .sub-menu ul.menu {
  font-family: Arial, sans-serif;
  display:flex;
}
header .sub-menu ul.menu li {
  /* 자식 요소가 이 값을 기준으로 이동할 수 있도록. */
  position:relative;
}
header .sub-menu ul.menu li::before {
  content: "";
  /* 인라인 요소는 너비를 직접 지정할 수 없으므로. */
  /* 포지션을 앱솔루트로 지정할 경우
  디스플레이가 블럭으로 지정이 되지만
  명시적으로 지정한다. */
  display: block;
  width: 1px;
  height: 12px;
  background-color: #e5e5e5;
  /* 부모 위치를 기준으로 이동하기 위해. */
  position: absolute;
  top: 0;
  bottom: 0;
  margin: auto 0;
}
header .sub-menu ul.menu li:first-child::before {
  display: none;
}
header .sub-menu ul.menu li a {
  font-size: 12px;
  /* 폰트의 크기는 작더라도
  패딩의 크기는 늘려
  사용자가 a 태그를 쉽게 클릭할 수 있도록 만들어야한다. */
  padding: 11px 16px;
  /* 패딩 값 지정을 위해 인라인 요소를 블럭 요소로 지정한다. */
  display:block;
  color: #656565;
}
header .sub-menu ul.menu li a:hover {
  color: #000;
}
header .sub-menu .search {
  height:34px;
  position:relative;
}
header .sub-menu .search input {
  width: 36px;
  height: 34px;
  padding: 4px 10px;
  border: 1px solid #ccc;
  box-sizing: border-box;
  border-radius: 5px;
  outline:none;
  background-color: #fff;
  color: #777;
  font-size: 12px;
  transition: width .4s;
}
header .sub-menu .search input:focus {
  width: 190px;
  border-color: #669900;
}
header .sub-menu .search .material-icons {
  height: 24px;
  position:absolute;
  top: 0;
  bottom: 0;
  right: 5px;
  margin: auto; 
  transition: .4s;
}
header .sub-menu .search.focused .material-icons {
  opacity: 0;
} 




/* maun-menu */
/* maun-menu */
/* maun-menu */
header .main-menu {
  position: absolute;
  bottom: 0;
  right: 0;
  z-index: 1;
  display: flex;
}
header .main-menu .item {

}
header .main-menu .item__name {
  padding: 10px 20px 34px 20px;
  font-family: Arial, sans-serif;
  font-size:  13px;
}
header .main-menu .item:hover .item__name {
  background-color: #2c2a29;
  color:#669900;
  border-radius: 6px 6px 0 0;
}
header .main-menu .item .item__contents {
  width: 100%;
  position: fixed;
  left: 0;
  display: none;
}
header .main-menu .item:hover .item__contents {
  display: block;
}
header .main-menu .item .item__contents .contents__menu {
  background-color: #2c2a29;
}
header .main-menu .item .item__contents .contents__menu > ul {
  display:flex;
  padding: 20px 0;
}
header .main-menu .item .item__contents .contents__menu > ul  > li {
    width: 220px;
}
header .main-menu .item .item__contents .contents__menu > ul > li h4 {
  padding: 3px 0 12px 0;
  font-size: 14px;
  color: #fff;
}
header .main-menu .item .item__contents .contents__menu > ul > li ul li {
  padding: 5px 0;
  font-size: 12px;
  color: #999;
  cursor: pointer;
}
header .main-menu .item .item__contents .contents__texture {
  padding: 26px 0;
  font-size: 12px;
  background-image: url("../assets/images/main_menu_pattern.jpg");
}
header .main-menu .item .item__contents .contents__texture h4 {
  color: #999;
  font-weight: 700;
}
header .main-menu .item .item__contents .contents__texture p {
  color: #669900;
  margin: 4px 0 14px;
  font-size: 12px;
}
</style>