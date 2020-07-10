<template>
  <div class="header">
    <ul class="ul-one">
      <li><i style="fontSize:35px;" class="iconfont icon-scan-line"></i></li>
      <li><el-input class="in" placeholder="华为充电宝" append="搜索" suffix="搜索" prefix-icon="el-icon-search" suffix-icon="el-icon-camera"></el-input></li>
      <li><i class="iconfont icon-hongbao"></i></li>
      <li style="marginTop:5px;"><img src="@img/right-icon.png" alt=""></li>
    </ul>
  </div>
</template>

<script>
export default {
    name:'Header'
}
</script>

<style scoped>
.header{
    position: fixed;
    top: 0;
    z-index: 99;
    opacity: 1;
}

.ul-one{
  display: flex;
  justify-content: space-around;
  background-color: #fff;
  width: 100vw;
  height: 50px;
}

.ul-one li{
  line-height: 40px;
  text-align: center;
  list-style: none;
}
.ul-one li:nth-of-type(3) i{
  font-size: 30px !important;
  color: red;
  background-color: orange;
  border-radius: 50px;
}
</style>