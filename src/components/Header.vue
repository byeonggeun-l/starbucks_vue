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
        <div class="search">
          <input type="text">
          <div class="material-icons">
            search
          </div>
        </div>
      </div>
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
    testda() {
      if (true) {
        
      } else {
        
      }
    },
    testd2() {
      
    }
  }
}
</script>

<style>
header {
  background-color: royalblue;
}
header .inner {
  width: 1100px;
  height: 120px;
  /* 자식 요소들이 해당 요소를 기준으로
  움직일 수 있도록 position: relative 로 설정한다. */
  position: relative;
  /* 상단과 하단의 값은 주지 않고,
  좌우 여백을 자동으로 주기 때문에
  좌우 정렬이 된다. */
  margin: 0 auto;
  background: orange;
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
  display: none;
}
header .sub-menu {
  
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

}
header .sub-menu .search input{

}
header .sub-menu .search .material-icons{

}
</style>