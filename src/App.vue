<template>

  <div class="black-bg" v-if="modalStatus == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p @click="modalStatus = false">모달 닫기</p>
    </div>
  </div>


  <div class="menu">
    <a v-for=" value in menuNames" :key="value">{{ value }}</a>
  </div>


  <!-- 이미지 경로 / src부터 시작할 경우 @/assets    /
    ./ 같은 디렉토리 ../ 상위 디렉토    -->
  <img src="./assets/logo.png" class="img1">
  <div v-for="(a, i) in products" :key="i">
    <h4>{{products[i]}}</h4>
    <p>{{prices[i]}}만원</p>
  </div>
  <div>
    <h4 @click="modalStatus = true">{{products[0]}}</h4>
    <p>{{prices[0]}}</p>
    <button @click="신고수[0] += 100">허위매물신고</button>
    <span>신고수 : {{신고수[0]}}</span>
    <button @click="increase">허위매물신고</button>
    <span>신고수 : {{신고수[1]}}</span>
  </div>

</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      modalStatus : false,
      신고수 : [0,0],
      prices : [60, 50],
      color1 : 'color : blue',
      products : ['역삼', '선릉'],
      menuNames : ['Home', 'Shop', 'About']
    }
  },
  methods: {
    increase(){
      this.신고수[1] += 1;
    }
  },
  components: {

  }
}
</script>

<style>
body {
  margin: 0
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
•white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.img1 {
  width: 30%;
  margin-top: 40px;
}

.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color : white;
  padding: 10px;
}
</style>
