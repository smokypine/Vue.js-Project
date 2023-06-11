<template>
  <div id="page">
    <div class="container">
      <div class="image-container" style="z-index:9998;">
        <iframe :src="currentImageSrc" frameborder="0" width="740" height="650"></iframe>
      </div>
      <div class="menu-container">
        <div id="homeMenu" class="vertical-menu">
          <a href="#recommend_trip" class="menu-item">이 주의 추천 여행지</a>
          <a href="#checkthisout" class="menu-item">이 상품 어때요?</a>
          <a href="#hotEurope" class="menu-item">지금 가장 HOT 유럽</a>
          <a href="#honeymoon" class="menu-item">2023 허니문 특가</a>
          <a href="#foundlife" class="menu-item">찾았다! 인생여행지!</a>
          <a href="#korea" class="menu-item">국내 출발확정</a>
        </div>
      </div>
    </div>
    <div class="image-buttons">
      <div
        v-for="(image, index) in images"
        :key="index"
        class="image-button"
        :class="{ active: currentIndex === index }"
        @click="resetTimer(index)"
      >
        {{ index + 1 }}
      </div>
    </div>
    <br>
    <hr size="7" noshade>
    <div id="recommend_trip">
      <h2 style="margin-left:30px; text-align:left;">이 주의 추천 여행지</h2>
      <table class="recommend_img">
        <tr>
          <td class="scale">
            <router-link to="/mysaipan">
              <a href="#">
                <img
                  src="@/assets/MainPage/recommend/saipan.jpg"
                  width="200"
                  @mouseover="hoverImage"
                  @mouseleave="unhoverImage"
                />
              </a>
            </router-link>
          </td>
          <td class="scale">
            <a href="#">
              <img
                src="@/assets/MainPage/recommend/hawaii.jpg"
                width="200"
                @mouseover="hoverImage"
                @mouseleave="unhoverImage"
              />
            </a>
          </td>
          <td class="scale">
            <router-link to="/myguam">
              <a href="#">
                <img
                  src="@/assets/MainPage/recommend/guam.jpg"
                  width="200"
                  @mouseover="hoverImage"
                  @mouseleave="unhoverImage"
                />
              </a>
            </router-link>
          </td>
          <td class="scale">
            <router-link to="/mydanang">
              <a href="#">
                <img
                  src="@/assets/MainPage/recommend/danang.jpg"
                  width="200"
                  @mouseover="hoverImage"
                  @mouseleave="unhoverImage"
                />
              </a>
            </router-link>
          </td>
        </tr>
        <tr>
          <th><router-link to="/mysaipan">사이판</router-link></th>
          <th><a href="">하와이</a></th>
          <th><router-link to="/myguam">괌</router-link></th>
          <th><router-link to="/mydanang">다낭</router-link></th>
        </tr>
      </table>
    </div>
    <hr size="7" noshade>
    <router-link to="/mycovid">
      <a href=""><img src="@/assets/MainPage/coronabanner.png" width="995"></a>
    </router-link>
    <hr size="7" noshade>

    <div id="checkthisout">
      <h2 style="margin-left:30px; text-align:left;">이 상품 어때요?</h2>
      <br>
      <table>
        <tr>
          <td><a href=""><img src="@/assets/MainPage/checkthisout/main01.jpg" width="280"></a></td>
          <td><a href=""><img src="@/assets/MainPage/checkthisout/main02.jpg" width="280"></a></td>
          <td><a href=""><img src="@/assets/MainPage/checkthisout/main03.jpg" width="280"></a></td>
        </tr>
        <tr>
          <td><a href="">북해도/샤코탄반도/후라노/비에이 5일</a></td>
          <td><a href="">괌 두짓타니 디럭스 오션프론트룸 4/5일</a></td>
          <td><a href="">[하와이] 초특급 하얏트 리젠시 6/7/8일</a></td>
        </tr>
        <tr style="color:red">
          <td>1,499,000원~</td>
          <td>1,172,900원~</td>
          <td>2,715,000원~</td>
        </tr>
        <tr>
          <td><a href=""><img src="@/assets/MainPage/checkthisout/main04.jpg" width="280"></a></td>
          <td><a href=""><img src="@/assets/MainPage/checkthisout/main05.jpg" width="280"></a></td>
          <td><a href=""><img src="@/assets/MainPage/checkthisout/main06.jpg" width="280"></a></td>
        </tr>
        <tr>
          <td><a href="">사이판 켄싱턴 호텔 로얄디럭스룸 4/5일 ★기사가이드경비포함★</a></td>
          <td><a href="">[휴양형/노쇼핑] 다낭/호이안 3박4일 [초특급 빈펄 남호이안]</a></td>
          <td><a href="">[도전최저가] 세부 솔레아 리조트 3박5일</a></td>
        </tr>
        <tr style="color:red">
          <td>1,115,400원~</td>
          <td>785,000원~</td>
          <td>580,600원~</td>
        </tr>
        <tr>
          <td><a href=""><img src="@/assets/MainPage/checkthisout/main07.jpg" width="280"></a></td>
          <td><a href=""><img src="@/assets/MainPage/checkthisout/main08.jpg" width="280"></a></td>
          <td><a href=""><img src="@/assets/MainPage/checkthisout/main09.jpg" width="280"></a></td>
        </tr>
        <tr>
          <td><a href="">[호핑투어+반딧불투어] 코타키나발루 인생샷 5/6일</a></td>
          <td><a href="">[국적기 직항 탑승] 터키 프리미엄 일주 9/10일</a></td>
          <td><a href="">[방콕파타야 5일/6일] 요트크루즈+스노쿨링+무앙보란+핵심관광</a></td>
        </tr>
        <tr style="color:red">
          <td>599,000원~</td>
          <td>1,699,000원~</td>
          <td>1,094,600원~</td>
        </tr>
      </table>
      <br>
      <p style="text-align:right;"><a href="#top">맨 위로</a></p>
    </div>
    <hr size="7" noshade>

    <div id="hotEurope">
      <h2 style="margin-left:30px; text-align:left;">지금 가장 HOT 유럽</h2>
      <br>
      <table>
        <tr>
          <td><a href=""><img src="@/assets/MainPage/hoteurope/eu01.webp" width="280"></a></td>
          <td><a href=""><img src="@/assets/MainPage/hoteurope/eu02.webp" width="280"></a></td>
          <td><a href=""><img src="@/assets/MainPage/hoteurope/eu03.webp" width="280"></a></td>
        </tr>
        <tr>
          <td><a href="">■마감임박■[노옵션/노쇼핑] 북유럽 품격여행 4국 9일</a></td>
          <td><a href="">■마감임박■ 스페인/포르투갈 완벽일주 9일</a></td>
          <td><a href="">■왕복직항■ 동유럽+발칸베스트 9일[플리트비체+블레드+4성1박업글+2대야경]</a></td>
        </tr>
        <tr style="color:red">
          <td>2,899,000원~</td>
          <td>1,599,000원~</td>
          <td>1,899,000원~</td>
        </tr>
        <tr>
          <td><a href=""><img src="@/assets/MainPage/hoteurope/eu04.webp" width="280"></a></td>
          <td><a href=""><img src="@/assets/MainPage/hoteurope/eu05.webp" width="280"></a></td>
          <td><a href=""><img src="@/assets/MainPage/hoteurope/eu06.webp" width="280"></a></td>
        </tr>
        <tr>
          <td><a href="">■출발확정■ 이탈리아 완벽일주 9일 《★전일정 4성호텔/ ★럭셔리 아울렛/ 친퀘테레/ 치비타/ 바티칸하</a></td>
          <td><a href="">■ 에미레이트ㅣ에티하드 항공 탑승 ■ 두바이/아부다비 완벽 일주 6일</a></td>
          <td><a href="">■ 두바이 시티투어 포함 ■ 두바이/터키일주 9일 [5대 옵션/월드체인 2박/전일정 5성 특급호텔/9대 특식]</a></td>
        </tr>
        <tr style="color:red">
          <td>1,549,000원~</td>
          <td>899,000원~</td>
          <td>1,099,000원~</td>
        </tr>
      </table>
      <br>
      <p style="text-align:right;"><a href="#top">맨 위로</a></p>
    </div>
    <hr size="7" noshade>
    <div id="honeymoon">
      <h2 style="margin-left:30px; text-align:left;">2023허니문 특가</h2><br>
      <router-link to="/myhoneymoon">
        <a href=""><img src="@/assets/MainPage/honeymoon.jpg" width="995"></a>
      </router-link>
      <br><br>
      <p style="text-align:right;"><a href="#top">맨 위로</a></p>
    </div>
    <hr size="7" noshade>
    <div id="foundlife">
      <h2 style="margin-left:30px; text-align:left;">찾았다! 인생여행지!</h2><br>
      <router-link to="/myphili">
        <a href=""><img src="@/assets/MainPage/phili.jpg" width="995"></a>
      </router-link>
      <br><br>
      <p style="text-align:right;"><a href="#top">맨 위로</a></p>
    </div>
    <hr size="7" noshade>
    <div id="korea">
      <h2 style="margin-left:30px; text-align:left;">국내출발확정</h2><br>
      <table>
        <tr>
          <td><a href=""><img src="@/assets/MainPage/korea/kor01.webp" width="280"></a></td>
          <td><a href=""><img src="@/assets/MainPage/korea/kor02.webp" width="280"></a></td>
          <td><a href=""><img src="@/assets/MainPage/korea/kor03.webp" width="280"></a></td>
        </tr>
        <tr>
          <td><a href="">[KTX] ★평창관광택시★ 택시로 한바퀴! 대관령하늘목장+오대산 월정사(당일)</a></td>
          <td><a href="">[KTX] ★평창관광택시★ 평창 캠크닉! 대관령 하늘목장+캠핑다이닝(당일)</a></td>
          <td><a href="">*무조건 출발보장* [BEST 추천] 제주특가투어(새별오름+족욕체험) 관광호텔(3일)</a></td>
        </tr>
        <tr style="color:red">
          <td>102,000원~</td>
          <td>139,000원~</td>
          <td>390,000원~</td>
        </tr>
        <tr>
          <td><a href=""><img src="@/assets/MainPage/korea/kor04.webp" width="280"></a></td>
          <td><a href=""><img src="@/assets/MainPage/korea/kor05.webp" width="280"></a></td>
          <td><a href=""><img src="@/assets/MainPage/korea/kor06.webp" width="280"></a></td>
        </tr>
        <tr>
          <td><a href="">★KTX+영주관광택시 실속형★ 소백힐링! 소백산국립공원+부석사+무섬마을</a></td>
          <td><a href="">★KTX+영주관광택시 일반형★ 영주 부석사+소수서원(선비촌)+무섬마을</a></td>
          <td><a href="">부산출발 [노팁노옵션 PERFECT 마라도투어] 제주오션스위츠호텔 3일</a></td>
        </tr>
        <tr style="color:red">
          <td>92,000원~</td>
          <td>99,000원~</td>
          <td>450,000원~</td>
        </tr>
        <tr>
          <td><a href=""><img src="@/assets/MainPage/korea/kor07.webp" width="280"></a></td>
        </tr>
        <tr>
          <td><a href="">부산출발 [BEST 추천] 제주특가투어 제주오션스위츠호텔 3일</a></td>
        </tr>
        <tr style="color:red">
          <td>360,000원~</td>
        </tr>
      </table>
      <br>
      <p style="text-align:right;"><a href="#top">맨 위로</a></p>
    </div>
    <hr size="7" noshade>
    <section>
      <img src="@/assets/MainPage/ARS1.jpg" width="975" usemap="#eventmap">
      <map name="eventmap">
        <area shape="rect" coords="511,92,604,138" href="#" alt="ARS 상담번호 안내" @click="openImage">
      </map>
    </section>
    <hr size="7" noshade>
  </div>
</template>

<script>
export default {
  data () {
    return {
      images: [
        require('@/assets/MainPage/iframe/air.jpg'),
        require('@/assets/MainPage/iframe/southeastasia.jpg'),
        require('@/assets/MainPage/iframe/america.jpg'),
        require('@/assets/MainPage/iframe/canada.jpg'),
        require('@/assets/MainPage/iframe/europe.jpg'),
        require('@/assets/MainPage/iframe/pacific.jpg'),
        require('@/assets/MainPage/iframe/korea.jpg')
      ],
      currentIndex: 0,
      intervalId: null
    }
  },
  computed: {
    currentImageSrc () {
      return this.images[this.currentIndex]
    }
  },
  mounted () {
    this.startAutoChange() // 페이지 로드 후 자동 변경 시작
  },
  beforeUnmount () {
    this.stopAutoChange() // 컴포넌트 해제 전 자동 변경 중지
  },
  methods: {
    openImage () {
      window.open(require('@/assets/MainPage/ARS2.jpg'), '_blank', 'width=1000,height=1000')
    },
    startAutoChange () {
      this.intervalId = setInterval(this.changeImage, 5000) // 4초마다 이미지 변경
    },
    stopAutoChange () {
      clearInterval(this.intervalId)
    },
    changeImage () {
      this.currentIndex++
      if (this.currentIndex >= this.images.length) {
        this.currentIndex = 0
      }
    },
    resetTimer (index) {
      this.currentIndex = index
      clearInterval(this.intervalId) // 타이머 초기화
      this.startAutoChange() // 타이머 재시작
    },
    hoverImage (event) {
      const img = event.target
      img.style.transform = 'scale(1.2)' // 이미지를 1.2배 확대
    },
    unhoverImage (event) {
      const img = event.target
      img.style.transform = 'scale(1)' // 이미지를 원래 크기로 되돌림
    }
  }
}
</script>

<style scoped>
#page {
  width: 995px;
  margin: 0 auto;
}

.container {
  display: flex;
  position: relative;
}

.image-container {
  margin-top: 20px;
  flex: 1;
  display: flex;
  justify-content: center;
}

.image-buttons {
  display: flex;
  justify-content: center;
}

.image-button {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  background-color: #ccc;
  margin: 0 5px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}
.image-buttons {
  position: absolute;
  bottom: -10px;
  left: 45%;
  transform: translateX(-50%);
  display: flex;
}

.image-button.active {
  background-color: #555;
  color: #fff;
}

.menu-container {
  margin-top: 20px;
  width: 225px;
}

.vertical-menu {
  height: 615px;
  background-color: #f2f2f2;
  overflow-y: auto;
}

.menu-item {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px;
  text-decoration: none;
  color: #333;
  height: 82px;
  font-size: 21px;
  font-weight: bold;
}

.menu-item:hover {
  background-color: #ddd;
}

.recommend_img {
  margin-top: 10px;
}

.recommend_img td {
  padding: 20px; /* Add spacing around each image */
}

#recommend_trip {
  border: solid 1px #cccccc;
  padding: 10px; /* Add padding to create space between the border and section content */
}

.scale img {
  transition: transform 0.3s ease-in-out;
}
#checkthisout{
  border: solid 1px #cccccc;
  padding:5px;
}
#hotEurope{
  border: solid 1px #cccccc;
  padding:5px;
}
#korea{
  border: solid 1px #cccccc;
  padding:5px;
}
</style>
