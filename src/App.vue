<template>

  <div class="menu">
    <a v-for="i in 메뉴들" :key="i"> {{ i }}</a>
  </div>

  <img alt="Vue logo" src="./assets/logo.png">
  <!--
  <div v-for="(a, i) in products" :key="i">
    <h4> {{ a }}</h4>
    <p>50</p>  
  </div>
  -->
  
  <div>
    <h4>{{products[0]}}</h4>
    <p>50</p>
    <button @click="신고수[0] += 1">허위매물신고</button> <span>신고 수 : {{ 신고수[0] }}</span>
  </div>
  <div>
    <h4>{{products[1]}}</h4>
    <p>60</p>
    <button @click="신고수[1]++">허위매물신고</button> <span>신고 수 : {{ 신고수[1]}} </span>
  </div>
  <div>
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
</style>
