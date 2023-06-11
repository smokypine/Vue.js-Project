<template>
  <div id="page">
    <nav class="image-container">
        <img src="@/assets/corona/co01.jpg" width="995">
        <img src="@/assets/corona/co02.jpg" width="995">
        <img src="@/assets/corona/co03.jpg" width="995">
        <div style="text-align:center">
            <a href="http://home.ewhalab.co.kr/corona/reservation.php" target="_blank"><img src="@/assets/corona/co04.png"></a>
        </div>
    </nav>
  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  },
  methods: {

  }
}
</script>

<style scoped>
#page {
  width: 995px;
  margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}

.image-container {
    width:995px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}
#pack{
    width:995px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  border: solid 1px #cccccc;
}
td{
  border: 1px solid #ccc;
}
#left{
  text-align:left;
}
#right{
  text-align:right;
}
#last{
    width:995px;
    text-align:right;
}
</style>
