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
      <Header_MainMenu 
        :items="headerItems"
      />
    </div>    
    <div
      ref="refBadges"
      class="badges"
    >
      <Badge 
        :path="'images/badge1.jpg'"
        :alt="'Badge'"
      />
      <Badge 
        :path="'images/badge2.jpg'"
        :alt="'Badge'"
      />
      <Badge 
        :path="'testimages/badge3.jpg'"
        :alt="'Badge'"
      />
    </div>
  </header>
</template>

<script>

import Header_MainMenu from '@/components/Header_MainMenu.vue'
import Badge from '@/components/Badge.vue'
import { throttle } from 'lodash';
import gsap from "gsap";


export default {
  name: "Header",
  components: {
    Header_MainMenu,
    Badge,
  },
  data() {
    return {
      offsetTops:[''],
      headerItems:[
        {
          'itemMainTitle':'COFFEE',
          'items':[
            {
              'itemSubTitle':'커피',
              'items':['스타벅스 원두', '스타벅스 비아', '스타벅스 오리가미']
            },
            {
              'itemSubTitle':'에스프레소 음료',
              'items':['도피오','에스프레소 마키아또','아메리카노','마키아또','카푸치노','라떼','모카','리스트레또 비안코',]
            },
            {
              'itemSubTitle':'커피 이야기',
              'items':['스타벅스 로스트 스팩트럼','최상의 아라비카 원두','한 잔의 커피가 완성되기까지','클로버® 커피 추출 시스템']
            },
            {
              'itemSubTitle':'최상의 커피를 즐기는 법',
              'items':['커피 프레스','푸어 오버','아이스 푸어 오버','커피 메이커','리저브를 매장에서 다양하게 즐기는 법',]
            },
          ],
          'texture':[
            {
              title:'나와 어울리는 커피 찾기',
              content:'스타벅스가 여러분에게 어울리는 커피를 찾아드립니다.'
            },
            {
              title:'최상의 커피를 즐기는 법',
              content:'여러가지 방법을 통해 다양한 풍미의 커피를 즐겨보세요.'
            }
          ]
        },
        {
          'itemMainTitle':'MENU',
          'items':[
            {
              'itemSubTitle':'음료',
              'items':['콜드 브루','브루드 커피','에스프레소','프라푸치노',
                '블렌디드 음료','스타벅스 피지오','티(티바나)','기타 제조 음료','스타벅스 주스(병음료)']
            },
            {
              'itemSubTitle':'푸드',
              'items':['베이커리','케익','샌드위치 & 샐러드','따뜻한 푸드',
                '과일 & 요거트','스낵 & 미니 디저트','아이스크림']
            },
            {
              'itemSubTitle':'상품',
              'items':['머그','글라스','플라스틱 텀블러','스테인리스 텀블러',
                '보온병','액세서리','커피 용품','패키지 티(티바나)']
            },
            {
              'itemSubTitle':'카드',
              'items':['실물카드','e-Gift 카드']
            },
            {
              'itemSubTitle':'메뉴 이야기',
              'items':['콜드 브루','스타벅스 티바나']
            },
          ],
          'texture':[
            {
              title:'스타벅스 티바나',
              content:'다양한 찻잎과 향신료 등 개성있는 재료로 새로운 맛과 향의 티를 선보입니다.'
            },
          ]
        },
        {
          'itemMainTitle':'STORE',
          'items':[
            {
              'itemSubTitle':'매장 찾기',
              'items':['퀵 검색','지역 검색','My 매장']
            },
            {
              'itemSubTitle':'매장 이야기',
              'items':['청담스타','티바나 인스파이어드 매장','파미에파크']
            },
          ],
          'texture':[
            {
              title:'매장 찾기',
              content:'보다 빠르게 매장을 찾아보세요.'
            },
            {
              title:'청담스타',
              content:'스타벅스 1,000호점인 청담스타점을 만나보세요.'
            },
          ]
        },
        {
          'itemMainTitle':'RESPONSIBILITY',
          'items':[
            {
              'itemSubTitle':'지역 사회 참여 활동',
              'items':['회망배달 캠페인','재능기부 카페 소식','커뮤니티 스토어',
                '청년인재 양성','우리 농산물 사랑 캠페인','우리 문화 지키기']
            },
            {
              'itemSubTitle':'환경보호 활동',
              'items':['환경 발자국 줄이기','일회용 컵 없는 매장','커피 원두 재활용']
            },
            {
              'itemSubTitle':'윤리 구매',
              'items':['윤리적 원두 구매','공정무역 인증','커피 농가 지원 활동']
            },
            {
              'itemSubTitle':'글로벌 사회 공헌',
              'items':['윤리경영 보고서','스타벅스 재단','지구촌 봉사의 달']
            },
          ],
          'texture':[
            {
              title:'커피원두 재활용',
              content:'스타벅스 커피 원두를 재활용 해보세요.'
            },
          ]
        },
        {
          'itemMainTitle':'MY STARBUCKS REWARDS',
          'items':[
            {
              'itemSubTitle':'마이 스타벅스 리워드',
              'items':['마이 스타벅스 리워드 소개','등급 및 혜택','스타벅스 별','자주하는 질문']
            },
            {
              'itemSubTitle':'스타벅스 카드',
              'items':['스타벅스 카드 소개','스타벅스 카드 갤러리','등록 및 조회',
                '충전 및 이용안내','분실신고/환불신청','자주하는 질문']
            },
            {
              'itemSubTitle':'스타벅스 카드 e-Gift',
              'items':['스타벅스 카드 e-Gift 소개','이용안내','선물하기','자주하는 질문']
            },
          ],
          'texture':[
            {
              title:'스타벅스 카드 등록하기',
              content:'카드 등록 후 리워드 서비스를 누리고 사용내역도 조회해보세요.'
            },
          ]
        },
        {
          'itemMainTitle':`WHAT'S NEW`,
          'items':[
            {
              'itemSubTitle':'프로모션 & 이벤트',
              'items':['전체','스타벅스 카드','마이 스타벅스 리워드','온라인','2017 스타벅스 플래너']
            },
            {
              'itemSubTitle':'새소식',
              'items':['전체','상품 출시','스타벅스의 문화','스타벅스 사회공헌','스타벅스 카드출시']
            },
            {
              'itemSubTitle':'매장별 이벤트',
              'items':['일반 매장','신규 매장']
            },
          ],
          'texture':[
            {
              title:'매장별 이벤트',
              content:'스타벅스의 매장 이벤트 정보를 확인 하실 수 있습니다.'
            },
            {
              title:'소셜 스타벅스',
              content:'다양한 스타벅스 SNS 채널을 통해 스타벅스를 만나보세요!'
            },
          ]
        },
      ],
    }
  },
  mounted() {
    // console.log(throttle);
    window.addEventListener('scroll', throttle(this.scrolling, 300));
  },
  methods:{
    clickSearch() {
      this.$refs.refSearchInput.focus();
      this.$refs.refSearch.classList.add('focused');
      this.$refs.refSearchInput.setAttribute('placeholder', '통합검색');
    },
    blurSearch() {
      this.$refs.refSearch.classList.remove('focused');
      this.$refs.refSearchInput.setAttribute('placeholder', '');
    },
    scrolling() {
      if (window.scrollY > 500) {
        gsap.to(this.$refs.refBadges, .6, {
          opacity: 0,
          display: 'none',
        });
      } else {
        gsap.to(this.$refs.refBadges, .6, {
          opacity: 1,
          display: 'block',
        });
      }
    }
  }
}
</script>




<style lang="scss">

</style>