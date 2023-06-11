<template>
<div id="page">
<br>
  <div id="logoimg">
    <router-link to="/">
      <img src="@/assets/MainPage/dong_img.png" alt="이미지" />
    </router-link>
  </div>
  <br>
  <div id="BS_card">
  <div id='address'>
      대표이사 : 김동현 | 사업자 등록번호 : 202-22-26001
    </div>
    <div id='customer'>
      고객센터 1544-4423
    </div>
    <br><br><br><br><br><br><br>
  </div>
</div>
</template>

<script>
export default {
  name: 'PageFooter',
  data () {
    return {
    }
  },
  methods: {
    toggleMenu () {
      this.showMenu = !this.showMenu
    }
  }
}
</script>

<style>
#top {
    float: right;
    margin: 10px 20px 0 0;
    width: 995px;
}
#page{
  width:995px;
  hight:200;
  margin:0 auto;
  margin-top: 10px;
}
#BS_card{
  border: solid 1px #cccccc;
}
#address{
  float: left;
  margin: 30px 0 0 20px;
}
#customer{
  float: right;
  margin: 30px 20px 0 20px;
}
</style>
