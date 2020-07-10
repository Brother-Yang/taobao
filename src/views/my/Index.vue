<template>
  <div style="height:1000px;">
    <ul class="ul-one">
      <li><i class="iconfont icon-fangzi1"></i><span style="font-size:12px;">亲情号</span></li>
      <li><i class="iconfont icon-shoucang1"></i></li>
      <li><i class="iconfont icon-ziyuan"></i></li>
      <li><i class="el-icon-setting"></i></li>
    </ul>
    <ul class="ul-two" style="height:50px;margin-left:10px;display:flex;">
      <i class="iconfont icon-wangwang" style="font-size:50px;color:orange;"></i>
      <p style="line-height:50px;margin-left:10px;font-size:20px;"><b>设置淘宝名称</b></p>
    </ul>
    <ul class="ul-three">
      <li><span>0</span><span>收藏夹</span></li>
      <li><span>3</span><span>关注店铺</span></li>
      <li><span>84</span><span>足迹</span></li>
      <li><span>0</span><span>红包卡券</span></li>
    </ul>
    <div class="div-four">
      <ul style="border-top-left-radius:10px;border-top-right-radius:10px;">
        <li><p><span class="span1">会员中心</span><span class="span2">看最新会员权益</span></p><i class="iconfont icon-hongbao"></i></li>
        <li><p><span class="span1">天猫积分</span><span class="span2">兑体检大额去券</span></p><i class="iconfont icon-hongbao"></i></li>
      </ul>
      <ul style="background-color:rgb(243, 243, 242);border-bottom-left-radius:10px;border-bottom-right-radius:10px;">
        <li><p><span class="span1">红包省钱卡</span><span class="span2">领91元红包</span></p><i class="iconfont icon-hongbao"></i></li>
        <li><p><span class="span1">红包签到</span><span class="span2">每天都能领红包</span></p><i class="iconfont icon-hongbao"></i></li>
      </ul>
    </div>
    <div class="div-five">
      <ul style="justify-content: space-between;font-size:13px;margin:10px 0;">
        <li style="margin-left:10px;"><b>我的订单</b></li>
        <li>查看全部订单 ></li>
      </ul>
      <ul>
        <li><i class="el-icon-s-finance"></i><span>待付款</span></li>
        <li><i class="el-icon-s-management"></i><span>待发货</span></li>
        <li><i class="iconfont icon-daishouhuo"></i><span>待收货</span></li>
        <li><i class="el-icon-chat-dot-round"></i><span>评价</span></li>
        <li><i class="iconfont icon-shouhou"></i><span>退款/售后</span></li>
      </ul>
    </div>
    <div class="div-img" style="height:150px;margin:20px 0;">
    </div>
    <el-carousel arrow="never" height="20vh" class="banner" loop>
      <el-carousel-item v-for="(item,index) in imgs" :key="index">
        <img :src="item" alt="" style="width:100%;">
      </el-carousel-item>
    </el-carousel>
    <div class="img-two">
      <img src="@img/10.jpg" alt="">
    </div>
    <NavBottom/>
  </div>
</template>

<script>
import NavBottom from '@c/NavBottom'
export default {
  name:'My',
  data (){
    return {
      imgs:[require('@img/8.png'),require('@img/9.png')]
    }
  },
  components:{
    NavBottom
  },
  methods: {
      
  }
}
</script>

<style lang="scss" scoped>
.ul-one{
  display: flex;
  justify-content: flex-end;
  li{
    margin: 10px;
    i{
      font-size: 20px;
    }
  }
}
.ul-three{
  display: flex;
  justify-content:space-around;
  li{
    display: flex;
    flex-direction: column;
    text-align: center;
    font-size: 12px;
    margin:10px 0; 
    span{
      display: inline-block;
      margin: 2px 0;
      color: rgb(59, 59, 59);
    }
  }
}
.div-four{
  display: flex;
  flex-direction: column;
  ul{
    display: flex;
    height: 70px;
    width: 95%;
    margin:  0 auto;
    background-color: rgb(253, 245, 229);
    li{
      flex: 1;
      display: flex;
      justify-content: space-around;
      margin: auto 0;
      i{
        font-size: 30px;
        color: red;
      }
      p{
        display: flex;
        flex-direction: column;
        .span1{
          font-size: 13px;
          font-weight: 600;
        }
        .span2{
          margin-top: 2px;
          font-size: 11px;
        }
      }
    }
  }
}
.div-five{
  width: 95%;
  margin:10px auto;
  ul{
    display: flex;
    justify-content: space-around;
    text-align: center;
    li{
      display: flex;
      flex-direction: column;
      i{
        font-size: 30px;
        color: orange;
        display: block;
        height: 30px;
      }
      span{
        margin: 5px 0;
        font-size: 13px;
      }
    }
  }
}
.div-img{
  background-image: url('../../assets/images/7.jpg');
  background-size: cover;
}
.img-two{
  margin-left: 20px;
  img{
    width: 95%;
  }
}
</style>