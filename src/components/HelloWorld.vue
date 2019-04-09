<template>
  <div >
    ============================流星雨============================
    <div class="title">
      <div id="stars"></div>
    </div>
  </div>
</template>

<script>
  import "./css/style.css"
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  mounted(){
    this.shootingStar();
  },
  methods:{
    shootingStar: function () {
      let stars = document.getElementById('stars')
      let star = document.getElementsByClassName('star')

// js随机生成流星
      for (let j = 0; j < 30; j++) {
        let newStar = document.createElement("div")
        newStar.className = "star"
        newStar.style.top = randomDistance(30, -30) + 'px'
        newStar.style.left = randomDistance(150, 20) + 'px'
        stars.appendChild(newStar)
      }

// 封装随机数方法
      function randomDistance(max, min) {
        let distance = Math.floor(Math.random() * (max - min + 1) * 20 + min)
        return distance
      }

// 给流星添加动画延时
      for (let i = 0, len = star.length; i < len; i++) {
        if (i % 3 == 0) {
          star[i].style.animationDelay = '0s'
        } else {
          star[i].style.animationDelay = i * 0.5 + 's'
        }
      }
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

  .title {
    background: url(//16129268.s61i.faiusr.com/4/AD0I9LnYBxAEGAAg7feE1AUo27qTMTCADzjeAg.png) 50% 50% no-repeat;
    background-size: cover;
    height: 1000px;
  }
</style>
