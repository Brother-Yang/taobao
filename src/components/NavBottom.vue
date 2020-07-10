<template>
  <div id="nav">
      <ul>
        <li><router-link to="/index"><i class="iconfont icon-1"></i><p>首页</p></router-link></li>
        <li><router-link to="/tao"><i class="iconfont icon-weitao"></i><p>微淘</p></router-link></li>
        <li><router-link to="/info"><i class="iconfont icon-xiaoxi"></i><p>消息</p></router-link></li>
        <li><router-link to="/shopcar"><i class="iconfont icon-gouwuche"></i><p>购物车</p></router-link></li>
        <li><router-link to="my"><i class="iconfont icon-ziyuan"></i><p>我的淘宝</p></router-link></li>
      </ul>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
#nav{
  width: 100vw;
  position: fixed;
  bottom: 0;
  overflow: hidden;
  background-color: #fff;
  z-index: 99;
}
*{
  padding: 0;
  margin: 0;
}
ul{
  display: flex;
}
i{
  font-size: 25px !important;
  font-weight: 1000;
}
li{
  flex: 1;
  list-style: none;
  text-align: center;
  font-size: 15px;
}
</style>