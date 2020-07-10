<template>
  <div id="index">
    <Header/>
    <div id="main">
        <ul class="ul-two">
          <li style="color:orange;">首页</li>
          <li>手机</li>
          <li>饰品</li>
          <li>女装</li>
          <li>医药</li>
          <li>百货</li>
          <li>进口</li>
          <li>鞋靴</li>
          <li>箱包</li>
          <li>数码</li>
          <li>母婴</li>
          <li>男装</li>
          <li>内衣</li>
          <li>美食</li>
          <li>美妆</li>
          <li>家装</li>
          <li>洗护</li>
          <li>企业</li>
          <li>车品</li>
          <li>电器</li>
          <li>保健</li>
          <li>生鲜</li>
          <!-- <li class="ico"><img src="@img/fixed-icon.png" alt=""></li> -->
        </ul>
        <!-- 轮播图 -->
        <template>
          <el-carousel arrow="never" height="20vh" class="banner" loop>
            <el-carousel-item v-for="(item,index) in imgs" :key="index">
              <img :src="item" alt="">
            </el-carousel-item>
          </el-carousel>
        </template>

        <ul class="ul-three">
          <li><img src="@img/slideicon1.png" alt=""></li>
          <li><img src="@img/slideicon1.png" alt=""></li>
        </ul>

        <!-- 百亿补贴 聚划算 -->
        <div class="div-four">
          <ul class="fout-one">
            <li>
              <span class="span1-one">
                <span class="span1-two">聚</span>
                <span class="span1-three">百亿补贴</span>
                <span class="span1-four">品牌正品</span>
              </span>
              <div class="imgs">
                <img src="@img/card-img03.png" alt="">
                <img src="@img/card-img04.png" alt="">
              </div>
            </li>
            <li>
              <span class="span3-one">
                <span class="span2-one">淘宝直播</span>
                <span class="span3-two">LIVE></span>
                <span class="span3-three">领券限时抢</span>
              </span>
              <div class="imgs2">
                <img src="@img/card-img07.png" alt="">
                <img src="@img/card-img08.png" alt="">
              </div>
            </li>
          </ul>
          <ul class="fout-one">
            <li>
              <span class="span1-one">
                <span style="font-weight:600;margin-left:10px;">聚划算</span>
              </span>
              <div class="imgs">
                <img src="@img/card-img02.png" alt="">
                <img src="@img/card-img01.png" alt="">
              </div>
            </li>
            <li>
              <span class="span3-one">
                <span class="span2-one">有好货</span>
                <span style="margin-left:2px;border-radius:3px;color:white;display:inline-block;font-size:12px;background-color:skyblue;width:50px;">品质好物</span>
                <span class="span3-three" style="color:skyblue;">全民口碑推荐</span>
              </span>
              <div class="imgs2">
                <img src="@img/card-img-09.png" alt="">
                <img src="@img/card-img07.png" alt="">
              </div>
            </li>
          </ul>
          <ul class="fout-one">
            <li>
              <span class="span1-one">
                <span style="font-weight:600;margin-left:10px;">天天特卖</span>
              </span>
              <div class="imgs">
                <img src="@img/card-img06.png" alt="">
                <img src="@img/card-img05.png" alt="">
              </div>
            </li>
            <li>
              <span class="span3-one">
                <span class="span2-one">每日好店</span>
                <span class="span3-two" style="background-color:orange;">精选</span>
                <span class="span3-three" style="color:orange;">挖深藏的店</span>
              </span>
              <div class="imgs2">
                <img src="@img/card-img07.png" alt="">
                <img src="@img/card-img11.png" alt="">
              </div>
            </li>
          </ul>
          <p><span>淘宝头条</span><span>热门</span>华为火力全开，5G新机全面开售<span></span></p>
        </div>

        <!-- 中间导航 -->
        <div class="div-five">
          <ul class="five-one">
            <li>全部</li>
            <li>猜你喜欢</li>
          </ul>
          <ul class="five-two">
            <li>直播</li>
            <li>新品搭配购</li>
          </ul>
          <ul class="five-two">
            <li>便宜好货</li>
            <li>低价抢购</li>
          </ul>
          <ul class="five-two">
            <li>买家秀</li>
            <li>真实晒单</li>
          </ul>
        </div>

        <!-- 数据 -->
        <div class="div-six">
          <ul class="six-one" v-for="item in arr" :key="item.id">
            <router-link :to="{name:'detail',params:{id:item.id}}">
              <img :src="item.img_arr[0]" alt="" class="so1">
                <span class="so2">{{item.name}}</span>
                <span class="so3">￥{{item.sale_price}}</span>
                <span class="so4">{{item.show_num}}人付款</span>
            </router-link>
          </ul>

        </div>
    </div>
    <NavBottom/>
  </div>
</template>

<script>
import NavBottom from '@c/NavBottom.vue'
import Header from '@c/Header.vue'
import { Loading } from 'element-ui'
export default {
    name:'Index',
    data(){
      return{
        imgs:[require('@img/1.jpg'),require('@img/2.jpg'),require('@img/3.jpg'),require('@img/4.jpg'),
        require('@img/5.jpg'),require('@img/6.jpg')
        ],
        arr:[]
      }
    },
    mounted(){
      this.showData();
    },
    methods:{
      showData(){
        window._api.getIndexData().then((res) => {
          this.arr = res.data;
        }).catch((err) => {
          console.log(err)
        });
      }
    },
    components:{
      NavBottom,Header
    }
}
</script>

<style scoped>

/* 全局 */

li{
  list-style: none;
}
*{
  padding: 0;
  margin: 0;
  /* background-color: rgb(238, 238, 238); */
}
#main{
  position: absolute;
  top: 50px;
}

/* div-six */
.div-six{
  width: 95%;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  text-align: center;
}
.six-one{
  margin: 5px 6px 10px 13px;
  border: 1px solid rgb(221, 131, 29);
}
.so1{
  display: block;
  width: 150px;
  margin: 5px 0;
}
.so2{
  display: block;
  width: 150px;
  font-size: 12px;
  margin: 3px 0;
}
.so3{
  font-size: 18px;
  color: orange;
}
.so4{
  display: inline-block;
  font-size: 12px;
  margin-left: 5px;
}


/* div-five */
.div-five{
  width: 100vw;
  display: flex;
  margin: 10px 0;
  text-align: center;
  justify-content: space-around;
}
.div-five .five-one li:first-child{
  font-weight: 550;
  color: rgb(243, 111, 34);
}
.div-five .five-one li:last-child{
  font-size: 12px;
  margin: 5px 0;
  background-color: orange;
  color: #fff;
  border-radius: 18px;
  padding: 1px;
}
.five-two li:first-child{
  font-weight: 550;
}
.five-two li:last-child{
  font-size: 12px;
  margin: 5px 0;
  color: rgb(206, 203, 203);
}


/* div-four */
.div-four{
  display: flex;
  width: 95vw;
  margin: 0 auto;
  flex-direction: column;
  border: 1px solid rgb(230, 230, 230);
}
.div-four ul {
  flex: 1;
  display: flex;
}
.imgs img{
  display: inline-block;
  margin: 10px 11px;
}
.span1-one{
  display:block;width:180px;margin:10px auto;
}
.span1-two{
  margin-left:3px;border-radius:5px;color:#fff;display:inline-block;height:20px;width:20px;background-color:red;text-align:center;
}
.span1-three{
  color:#FF4500;font-weight:1000;margin:0 8px;
}
.span1-four{
  font-size:15px;display:inline-block;height:18px;width:70px;color:#fff;background-color:orange;text-align:center;border-radius:5px;
}
.span2-one{
  font-weight:800;margin-left:10px;
}
.span3-one{
  display: block;
  margin-top:10px; 
}
.span3-two{
  display: inline-block;
  font-size: 10px;
  margin-left:2px;
  height: 12px;
  text-align: center;
  color: #fff;
  border-radius: 3px;
  width: 32px;
  background-color: rgb(235, 101, 124);
}
.span3-three{
  display: block;
  color: rgb(255, 126, 148);
  margin-left:10px; 
  margin-top:8px; 
  font-size: 12px;
}
.imgs2{
  margin: 5px 10px;
}
.div-four p span{
  display: inline-block;
}
.div-four p span:first-child{
  font-size: 15px;
  font-weight: 600;
  margin: 0 10px;
}
.div-four p span:nth-child(2){
  font-size: 12px;
  background-color: pink;
  color: rgb(201, 102, 67);
  border-radius: 3px;
  margin-right: 5px;
}
.div-four p:last-child{
  font-size: 13px;
}
.div-four p{
  margin: 5px 0;
}


/* ul-three */
.ul-three {
  width: 100vw;
  overflow: auto;
  display: flex;
}
.ul-three:first-child{
  padding-left: 10px;
}

/* 轮播图 */

.banner{
  width: 95vw;
  margin: 0 auto;
}
.el-carousel__item {
  color: #475669;
  font-size: 18px;
  opacity: 0.75;
  line-height: 300px;
  margin: 0;
}

/* ul-two */
.ul-two{
  overflow: scroll;
  width: 100vw;
  white-space:nowrap;
  position: relative;
  margin-bottom: 10px;
  /* margin-top: 5px; */
}
.ul-two .ico{
  position: absolute;
  left: 100px;
}
::-webkit-scrollbar {
  display: none; /* Chrome Safari */
}
.ul-two li{
  padding: 0 13px;
  display: inline-block;
  font-size: 18px;
}
</style>