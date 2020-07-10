<template>
  <div id="details" style="height:1000px;">

    <div class="header">
        <ul class="ul1">
            <li @click="back()"><i class="el-icon-arrow-left"></i></li>
            <li><el-input class="cn"  placeholder="水晶" prefix-icon="el-icon-search"></el-input></li>
            <li><i class="el-icon-share"></i></li>
            <li><i class="iconfont icon-gouwuche"></i></li>
            <li><i class="iconfont icon-more"></i></li>
        </ul>
    </div>

    <!-- main -->
    <div class="main">
        <div>
            <el-carousel height="300px" arrow="never" indicator-position="none" loop>
                <el-carousel-item v-for="item in arr.img_arr" :key="item">
                    <img :src="item" alt="" class="imgs">
                </el-carousel-item>
            </el-carousel>
        </div>
        <div class="one">
            <p style="margin:10px;"><span style="color:orange;font-size:20px;">￥{{this.arr.sale_price}}</span><span style="font-size:12px;color:rgb(192, 191, 191);margin-left:5px;">价格￥<span style="text-decoration:line-through;">{{this.arr.show_price}}</span></span></p>
            <ul class="one-ul">
                <p style="margin:10px;background-color:pink;width:60px;color:red;font-size:12px;">购买得积分</p>
                <p style="color:red;font-size:12px;margin:auto 0;">查看 ></p>
            </ul>
        </div>
        <div class="two">
            <ul style="display:flex;margin-left:10px;">
                <p style="font-size:15px;display:block;width:85%;">{{this.arr.name}}</p>
                <p style="border-top-left-radius:18px;border-bottom-left-radius:18px;line-height:20px;font-size:13px;opacity:0.5;display:block;background-color:#DCDCDC;height:20px;width:60px;text-align:center;">
                    <i class="el-icon-share"></i>
                    <span>分享</span>
                </p>
            </ul>
            <ul style="margin:5px 0;display:flex;justify-content:space-around;width:95%;">
                <li ><i class="iconfont icon-shoucang"></i><span style="margin-left:5px;font-size:13px;">推荐</span></li>
                <li ><i class="iconfont icon-ziyuan"></i><span style="margin-left:5px;font-size:13px;">帮我选</span></li>
            </ul>
        </div>
        <div class="three" style="margin:10px;">
            <ul style="margin:5px 0;display:flex;font-size:12px;justify-content: space-around;">
                <li>发货</li>
                <li><i class="el-icon-location-outline"></i> 北京</li>
                <li>快递:快递包邮</li>
                <li>月销9</li>
            </ul>
            <ul style="display:flex;font-size:12px;justify-content: space-around;">
                <li style="margin-left:-50px;">活动</li>
                <li><span>积分兑五元红包 </span><span>></span></li>
            </ul>
        </div>
        <div class="four">
            <ul>
                <li>保障</li>
                <li>隔日达 现在下单，预计7月10日送达</li>
                <li>></li>
            </ul>
        </div>
        <div class="imgs" v-for="item in this.arr.img_arr" :key="item">
            <img :src="item" alt="" style="width:100%;">
        </div>
    </div>

    <div class="footer">
        <ul class="ul2">
            <li class="li1"><i class="iconfont icon-dianpu"></i><span>店铺</span></li>
            <li class="li1"><i class="iconfont icon-wangwang"><span>客服</span></i></li>
            <li class="li1"><i class="iconfont icon-shoucang1"><span>收藏</span></i></li>
            <li class="li2"><span>加入购物车</span><span style="width:60px;">立即购买</span></li>
        </ul>
    </div>
  </div>
</template>

<script>
export default {
    name:'Datails',
    data(){
        return{
            arr:[],
            id:this.$route.params.id
        }
    },
    mounted(){
        this.show();
    },
    methods:{
        show(){
            window._api.getIndexData2({id:this.id}).then((res) => {
                this.arr = res;
            }).catch((err) => {
                
            });
        },
        back(){
            this.$router.go(-1)
        }
    }
}
</script>

<style lang="scss" scoped>
/* main */
.four{
    width:95%;
    margin: 0 auto;
    font-size: 12px;
    ul{
        display: flex;
        justify-content: space-around;
        margin: 10px 0;
    }
}
.main{
    margin-top:50px;
}
.imgs{
    width: 100%;
    height: 100%;
}
.one-ul{
    width: 95%;
    display: flex;
    justify-content: space-between;
}


/* header */
.header{
    position: fixed;
    top:0;
    z-index: 99;
    height: 50px;
    width: 100%;
    line-height: 50px;
    background-color: #fff;
}
.ul1{
    display: flex ;
    width: 100%;
    justify-content: space-around;
    font-size: 18px;
}
.ul1 i{
    font-size: 18px;
}

/* footer */
.footer{
    position: fixed;
    bottom: 0;
    width: 100%;
    z-index: 99;
    background-color: #fff;
}
.ul2{
    display: flex;
    justify-content:space-around;
    text-align: center;
}
.ul2 i{
    font-size: 20px;
}

.ul2 li span{
    display: block;
    font-size: 12px !important;
}
.li1{
    flex: 1;
    display: flex;
    flex-direction: column;
    margin: 2px 0;
}
.li2{
    flex: 4;
    margin: auto 0;
}
.li2 span{
    display: inline-block !important;
    line-height: 30px;
    background-color: orange;
    padding:0 10px;
    color: #fff;
    height: 30px;
}
.li2 span:first-child{
    border-top-left-radius:18px;
    border-bottom-left-radius:18px;
}
.li2 span:last-child{
    border-top-right-radius:18px;
    border-bottom-right-radius:18px;
    background-color: red;
}
</style>