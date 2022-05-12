<template>

  <div class="black-bg" v-if=" 모달창상태 == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <h4>상세페이지 세부내용</h4>
      <div @click="모달창상태 = false">
        <h5>닫기</h5>
      </div>
    </div>
  </div>


  <div class="menu">
    <a v-for="i in 메뉴들" :key="i"> {{ i }}</a>
  </div>

  <!--
  <div v-for="(a, i) in products" :key="i">
    <h4>{{ a }}</h4>
    <p>50</p>  
    <button @click="신고수[i] += 1">허위매물신고</button> 
    <span>신고 수 : {{ 신고수[i] }}</span>
  </div>
  -->
  
  <div>
    <img src="./assets/room0.jpg" class="room0">  
    <h4 @click="모달창상태 = true">{{products[0]}}</h4>  <!-- './' 는 '현재 경로'라는 뜻. 따라서 src에 있는거 가져올 때 경로는 ./ 부터 시작한다.-->
    <p>50</p>
    <button @click="신고수[0] += 1">허위매물신고</button> <span>신고 수 : {{ 신고수[0] }}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room1">
    <h4>{{products[1]}}</h4>
    <p>60</p>
    <button @click="신고수[1]++">허위매물신고</button> <span>신고 수 : {{ 신고수[1]}} </span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room2">
    <h4>{{products[2]}}</h4>
    <p>70</p>
    <button @click="신고수[2]++">허위매물신고</button> <span>신고 수 : {{ 신고수[2]}} </span> 
  </div>
  

</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      모달창상태: false,
      price : [50, 60, 70],
      스타일 : 'color : red',
      products : ['역삼동원룸', '대치동원룸', '한남동원룸'],
      메뉴들 : ['Home', 'Shop', 'About'],
      신고수 : [0, 0, 0],
    }
  },
  methods: {
    increase() {
      this.신고수[0] += 1;
    }

  },

  components: {
  }
}
</script>

<style>

body {
  margin: 0;
}

div {
  box-sizing: border-box; /* box-sizing 이거 나중에 따로 정리하자.*/ 
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;  /* 이것도 나중에따로 정리합시다. */
  padding: 20px;
}

.white-bg {
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
  margin-top: 60px;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 10px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room0, .room1, .room2 {
  width: 35%;
  height: 35%;
  margin-top: 40px;
}
</style>
