<template>
  <div id="top" class="menu-right">
    <p>
      <a href="#" @click="showLoginModal = true">로그인</a> |
      <a href="#">회원가입</a> |
      <a href="#">예약확인/결제</a> |
      <a href="#">고객센터</a>
    </p>
  </div>
  <div id="page">
    <br /><br /><br /><br />
    <div class="top-menu">
      <ul>
        <li v-for="(menu, index) in menus" :key="index" :class="{ 'active': menu.active }" @mouseover="showSubmenu(index)" @mouseout="hideSubmenu(index)">
          <span v-if="menu.link">
            <a :href="menu.link">{{ menu.name }}</a>
          </span>
          <span v-else-if="menu.name === '홈'" @click="openHome">{{ menu.name }}</span>
          <span v-else-if="menu.name === '허니문'" @click="openHoneymoon">{{ menu.name }}</span>
          <span v-else-if="menu.name === '호텔/펜션'" @click="openHotelPension">{{ menu.name }}</span>
          <span v-else @click="openHomeView">{{ menu.name }}</span>
          <ul class="submenu" v-if="menu.active || menu.submenuActive" @mouseover="menu.submenuActive = true" @mouseout="menu.submenuActive = false">
            <li v-for="(submenu, subIndex) in menu.submenus" :key="subIndex">
              <a :href="submenu.link">{{ submenu.name }}</a>
            </li>
          </ul>
        </li>
      </ul>
    </div>
    <div class="image-container">
      <router-link to="/"><img src="@/assets/MainPage/dong_img.png" alt="이미지" /></router-link>
    </div>
    <div class="modal-container" v-if="showLoginModal">
      <div class="modal-content">
        <h2>로그인</h2>
        <form @submit.prevent="login">
          <table>
            <tr>
              <td><label for="username">아이디:</label></td>
              <td><input type="text" id="username" v-model="username" required></td>
            </tr>
            <tr>
              <td><label for="password">비밀번호:</label></td>
              <td><input type="password" id="password" v-model="password" required></td>
            </tr>
            <tr>
              <td colspan="2">
                <button type="submit">로그인</button>
                <button @click="closeModal">닫기</button>
              </td>
            </tr>
          </table>
        </form>
        <p v-if="loggedIn">환영합니다 {{ username }}님</p>
        <p v-if="loginError" class="error-message">로그인에 실패했습니다. 다시 시도해주세요.</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TopMenu',
  data () {
    return {
      menus: [
        {
          name: '홈',
          active: false,
          submenuActive: false,
          link: null
        },
        {
          name: '해외여행',
          active: false,
          submenuActive: false,
          link: null,
          submenus: [
            { name: '사이판', link: '#' },
            { name: '괌', link: '#' },
            { name: '다낭', link: '#' },
            { name: '필리핀', link: '#' }
          ]
        },
        {
          name: '제주/국내여행',
          active: false,
          submenuActive: false,
          link: null,
          submenus: [
            { name: '제주도', link: '#' },
            { name: '강원도', link: '#' },
            { name: '경기도', link: '#' },
            { name: '충청도', link: '#' },
            { name: '경상도', link: '#' },
            { name: '전라도', link: '#' }
          ]
        },
        {
          name: '호텔/펜션',
          link: null,
          active: false,
          submenuActive: false
        },
        {
          name: '허니문',
          active: false,
          submenuActive: false
        }
        // 추가적인 메뉴와 서브메뉴를 여기에 추가할 수 있습니다.
      ],
      showLoginModal: false,
      username: '',
      password: '',
      loggedIn: false,
      loginError: false
    }
  },
  methods: {
    showSubmenu (index) {
      this.menus.forEach((menu, i) => {
        if (i !== index) {
          menu.active = false
        }
      })
      this.menus[index].active = true
    },
    hideSubmenu (index) {
      this.menus[index].active = false
    },
    openHoneymoon () {
      this.$router.push('/myhoneymoon')
    },
    openHome () {
      this.$router.push('/')
    },
    openHotelPension () {
      window.location.href =
        'https://www.booking.com/index.ko.html?ws=&errorv_ssb=empty&errorv_sb_price_type=total&=&gclid=CjwKCAjwvpCkBhB4EiwAujULMtBwZla7PVOLunQfErVtQLkNutRtuGTCuJ0uW7SzPX-KtXTasPF12RoCRMUQAvD_BwE&aid=318615&label=Korean_South_Korea-KO-KR-131246354044-lqHqiW6tNbRkHjsFQdmmhwS637818828162%3Apl%3Ata%3Ap1%3Ap2%3Aac%3Aap%3Aneg%3Afi%3Atiaud-297601666235%3Adsa-1227182654382%3Alp1009871%3Ali%3Adec%3Adm%3Aag131246354044%3Acmp400536625&errorv_label_click=undef&errorv_shw_aparth=1&errorv_top_ufis=1&errorv_room1=A%2CA&errorv_ss=%EC%84%9C%EC%B4%88+%ED%98%B8%ED%85%94%EC%8A%A4%ED%83%80+%ED%94%84%EB%A6%AC%EB%AF%B8%EC%96%B4%2C%EC%84%9C%EC%B4%88'
    },
    openHomeView () {
      this.$router.push('/')
    },
    login () {
      // 로그인 로직을 여기에 작성합니다.
      if (this.username === 'hayasdan' && this.password === 'drkim4926^') {
        this.loggedIn = true
        this.loginError = false
      } else {
        this.loggedIn = false
        this.loginError = true
      }
    },
    closeModal () {
      this.showLoginModal = false
      this.username = ''
      this.password = ''
      this.loggedIn = false
      this.loginError = false
    }
  }
}
</script>

<style scoped>
/* 기존의 스타일 */
#page {
  width: 995px;
  margin: 0 auto;
}
.top-menu {
  background-color: #f1f1f1;
  width: 100%;
  max-width: 995px;
  margin: 0 auto;
}

.top-menu ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
  display: flex;
  justify-content: flex-start;
}

.top-menu li {
  padding: 10px 20px;
  position: relative;
  cursor: pointer;
}

.top-menu li.active {
  background-color: #ccc;
}

.submenu {
  display: none;
  position: absolute;
  background-color: #fff;
  padding: 20px;
  top: 100%;
  left: 0;
}

.top-menu li:hover > ul.submenu {
  display: block;
}

.menu-right {
  float: right;
  width: 100%;
  max-width: 995px;
  margin-right: 10px;
}
.image-container {
  margin-top: 20px;
  display: flex;
  justify-content: center;
}
.modal-container {
  z-index:9999;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgba(0, 0, 0, 0.5);
}

.modal-content {
  background-color: white;
  padding: 20px;
  border-radius: 5px;
}

</style>
