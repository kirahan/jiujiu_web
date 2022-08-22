<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs

import { ref } from "vue"

// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
const bleconnect = ()=>{
  iserror.value = true
  // alert("未检测到设备，请先让设备连接到此wifi")
}

const hidealert = ()=>{
  iserror.value = false
  console.log(iserror)
}

const iserror = ref(false)

</script>

<template>
 <div class="main" @click="bleconnect">
  <div class="header">
    <img src="./assets/icon/Left.png" alt="">
    <span>秋千B123</span>
    <img src="./assets/icon/More.png" alt="">
  </div>

  <div class="product">
    <img src="./assets/qiuqian.png" alt="">
  </div>

  <div class="group group1">
    <span>已开启</span>
    <img src="./assets/icon/Shutdown.png" alt="">
  </div>
  <div class="group group2">
    <img src="./assets/icon/Minus.png" alt="">
    <div class="cont">
      <p class="time">15分钟</p>
      <p class="des">摇摆时长</p>
    </div>
    <img src="./assets/icon/Plus.png" alt="">
  </div>

  <div class="container_group">
    <div class="smallgroup">
      <p>暂停</p>
      <button></button>
    </div>
    <div class="smallgroup type2">
      <div class="left-div">
        <p class="left-top">零重力</p>
        <p class="left-bottom">关闭</p>
      </div>
      <img src="./assets/icon/User.png">
    </div>
  </div>

  <div class="container_group">
    <div class="smallgroup type2">
      <div class="left-div">
        <p class="left-top">精选程序</p>
        <p class="left-bottom">关闭</p>
      </div>
      <img src="./assets/icon/Heart.png">
    </div>
    <div class="smallgroup type2">
      <div class="left-div">
        <p class="left-top">心灵放松</p>
        <p class="left-bottom">关闭</p>
      </div>
      <img src="./assets/icon/Qiu.png">
    </div>
  </div>

  <div class="container_group">
    <div class="smallgroup type2">
      <div class="left-div">
        <p class="left-top">温度感应</p>
        <p class="left-bottom">关闭</p>
      </div>
      <img src="./assets/icon/Temperature.png">
    </div>
    <div class="smallgroup type2">
      <div class="left-div">
        <p class="left-top">影音娱乐</p>
        <p class="left-bottom">关闭</p>
      </div>
      <img src="./assets/icon/Music.png">
    </div>
  </div>

  <div class="container_group">
    <div class="smallgroup type2">
      <div class="left-div">
        <p class="left-top">速度调节</p>
        <p class="left-bottom">关闭</p>
      </div>
      <img id="l3" src="./assets/icon/Level3.png">
    </div>
    <div class="smallgroup type2" >
      <div class="left-div">
        <p class="left-top">幅度调节</p>
        <p class="left-bottom">关闭</p>
      </div>
      <img id="l5" src="./assets/icon/Level5.png">
    </div>
  </div>


  <div class="alert" v-show="iserror">
    <p>未检测到设备，请先让设备连接到此wifi</p>
    <button @click.stop="hidealert">确定</button>
  </div>
 </div>
</template>

<style scoped>

.main{
  width: 100vw;
  height: 100vh;
  /* liner background-color */
  background: linear-gradient(to top right,#BA46FF,#81FEBC);
}
.header{
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 50px;
  width: 100%;
  color: black;
}
.header img{
  padding-left: 10px;
  padding-right: 10px;
  width: 20px;
  height: 20px;
}

.header span{
  font-size: 20px;
  font-weight: bold;
  margin-left: 10px;
}

.product{
  padding-top: 50px;
  width: 100%;
  height: 200px;
}
.product img{
  width: 70%;
  height: 70%;
}

.group{
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: black;
  background-color: white;
  border-radius: 12px;
  margin-bottom: 20px;
}

.group1,.group2{
  margin-left: 5%;
  width: 90%;
  height: 80px;
}
.group1 span{
  padding-left: 20px;
  font-size: 16px;
  font-weight: bold;
}
.group1 img{
  width: 40px;
  height: 40px;
  padding-right: 10px;
}

.group2 img{
  width: 40px;
  height: 40px;
  padding-left: 10px;
  padding-right: 10px;
}

.group2 .cont p{
  margin: 0;
}
.group2 .time{
  font-size: 20px;
}
.group2 .des{
  font-size: 14px;
  color:gray;
}

.container_group {
  margin-left: 5%;
  width: 90%;
  height: 60px;
  display: flex;
  justify-content: space-between;
  padding-bottom: 20px;
}

.smallgroup{
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: black;
  background-color: white;
  border-radius: 12px;
  width:48%
}

.smallgroup p{
  padding-left:20px;
  margin: 0;
}

.smallgroup button{
  background-color: grey;
  border:black;
  width: 40px;
  height: 20px;
  margin-right:20px;
}

.type2 .left-div{
  padding-left: 10px;
  margin-top: 5px;
  text-align: left;
}

.left-div .left-top{
  font-size: 16px;
}
.left-div .left-bottom{
  font-size: 10px;
  color: #025CD7;
}

.type2 img{
  width: 40px;
  height: 40px;
  padding-right: 10px;
}

#l3{
  height: 10px;
}

#l5{
  height: 16px;
}

.alert{
  position: absolute;
  top: 10vh;
  left: 10vw;
  width: 80vw;
  height: 80vh;
  background-color: white;
  border-radius: 12px;
  text-align: center;
  padding-top: 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.alert p{
  font-size: 20px;
  font-weight: bold;
  color:black;
}

</style>
