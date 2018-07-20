<template>
    <div class="container">
        <banner/>
        <div class="fixedTitle">
            <div class="priceTitle lt">
                <p>
                    <span class="price">{{currency}}:{{price}}</span>
                    <span class="originalPrice">{{currency}}:{{originalPrice}}</span>
                </p>
                <p class="flashDeals">
                    <span><img src="../../static/img/clock.png">Flash deals</span>
                    <span class="progress">
                        <span id="progress">80%</span> 
                    </span>
                </p>
            </div>
            <div class="timeDown rt">
                <p>Ends In</p>
                <p class="downTime">
                    <span id="hour">{{hour}}</span> :
                    <span id="minute">{{minute}}</span> :
                    <span id="second">{{second}}</span>
                </p>
            </div>
        </div>
        <div class="soldProduct">
            <span class="soldNum">-6584-</span>
            <span>Sold</span>
        </div>
        <div class="productTitle">{{productTitle}}</div>
        <div class="guarantee clear">
            <p class="lt">
                <span>
                    <img src="../../static/img/trick.png">
                    Cash On Delivery 
                </span>
                <span>
                    <img src="../../static/img/trick.png">
                    Genuine Guarantee
                </span>
            </p>
            <p class="rt">
                <span>
                    <img src="../../static/img/trick.png">
                    Free Shipping  
                </span>
                <span>
                    <img src="../../static/img/trick.png">
                    7 Days Hassle Free Return
                </span>
            </p>
        </div>
        <review/>
        <productDetail/>
        <vedio/>
        <div class="purchaseGuide"></div>
        <div class="buyNow submitButton" @click="buyNow">Buy Now</div>
        <div class="selectProductShow" v-show="selectProductShow">
            <selectProduct/>
            <userMsg/>
            <complete/>
        </div>
    </div>
</template>
<script>
import Banner from '@/components/banner'
import Review from '@/components/review'
import ProductDetail from "@/components/productDetail";
import Vedio from "@/components/vedio";
import SelectProduct from "@/components/selectProduct";
import UserMsg from "@/components/userMsg";
import Complete from "@/components/complete";

export default {
    name: 'index',
    data () {
        return {
            currency: 'RM',
            price: '169',
            originalPrice: '399',
            productTitle: 'Hurricane Spin Duster',
            hour: '00',
            minute: '00',
            second: '00',
            selectProductShow: false
        }
    },
    components: {
        'test': {
            template:'<p>this is test</p>'
        },
        'banner': Banner,
        'review': Review,
        'productDetail': ProductDetail,
        'vedio': Vedio,
        'selectProduct': SelectProduct,
        'userMsg': UserMsg,
        'complete': Complete
    },
    methods:{
        timeDown:function (){
            var that=this;
            // console.log(this);
            function timer(intDiff){
                var interval = setInterval(function(){
                    var day=0,hour=0,minute=0,second=0,ms=0;      
                    if(intDiff > 0){
                        day = Math.floor(intDiff / (60 * 60 * 24));
                        hour = Math.floor(intDiff / (60 * 60)) - (day * 24);
                        minute = Math.floor(intDiff / 60) - (day * 24 * 60) - (hour * 60);
                        second = Math.floor(intDiff) - (day * 24 * 60 * 60) - (hour * 60 * 60) - (minute * 60);
                        ms = Math.floor(intDiff*1000) - (day * 24 * 60 * 60) - (hour * 60 * 60) - (minute * 60)-(second*1000);
                    }else {
                        clearInterval(interval);
                        interval = null;
                        getTime();
                    }
                    if (minute <= 9) minute = '0' + minute;
                    if (second <= 9) second = '0' + second;
                    intDiff--;
                    // document.getElementById("hour").innerHTML=hour;
                    // document.getElementById("minute").innerHTML=minute;
                    // document.getElementById("second").innerHTML=second;
                    that.hour=hour;//待做
                    that.minute=minute;
                    that.second=second;
                    // that.$set(that.second,'second',second);
                    // console.log(that);
                    // console.log(that.hour,that.minute,that.second)
                }, 1000);
            } 
            function getTime(){
                if(window.localStorage){
                    var timeSec = localStorage.getItem("time");
                    var now = new Date().getTime();
                    if(timeSec && now <= timeSec){
                        var secs = parseInt((timeSec - now)/1000);
                        timer(secs);
                    }else{
                        localStorage.setItem("time",new Date().getTime()+3600*1000);
                        timer(3600);
                    }
                }
            };
            getTime();
        },
        progressDown: function () {
            var start=80,end=98,interval=end-start,speed=30,totalTime=interval*speed,intervalSpeed=speed*1000,htmlProgress;
            function progress(inter){
                inter=Math.ceil(inter/speed);
                    if(inter < 0){
                        clearInterval(timeInterval);
                        timeInterval=null;
                    }else{
                        htmlProgress=(totalTime/speed-inter)+start;
                        document.getElementById("progress").innerHTML=htmlProgress+"%";
                        document.getElementById("progress").style.width=htmlProgress+"%";
                    }
                    inter--;
                var timeInterval=setInterval(function(){
                    if(inter < 0){
                        clearInterval(timeInterval);
                        timeInterval=null;
                    }else{
                        htmlProgress=(totalTime/speed-inter)+start;
                        document.getElementById("progress").innerHTML=htmlProgress+"%";
                        document.getElementById("progress").style.width=htmlProgress+"%";
                    }
                    inter--;
                },intervalSpeed)
            }
            function get(){
                if(window.localStorage){
                    var now=parseInt(new Date().getTime())/1000;
                    var localTime=localStorage.getItem("localTime");
                    if(localTime != null){
                        if(localTime<now){
                            document.getElementById("progress").innerHTML="98%";
                            document.getElementById("progress").style.width="98%";
                        }else if(localTime>now){
                            var inter=parseInt(localTime-now);
                            progress(inter)
                        }
                    }else{
                        progress(totalTime)
                        localStorage.setItem("localTime",parseInt(new Date().getTime()/1000)+totalTime);
                    }  
                }
            }
            get();
        },
        buyNow: function () {
            this.selectProductShow=true;
            // console.log(this.selectProductShow)
        }
    },
    created: function () {//在一个实例被创建之后执行代码
        // this.progressDown()
    },
    mounted: function () {
        this.timeDown(),
        this.progressDown()//问题：30秒时间戳过后才显示原来的变化

    },
    updated: function ()  {
        
    },
    destroyed: function () {
    },
    computed: {
        
    }
}
</script>
<style>
@import '../../static/css/base.css';
@import '../../static/css/index.css';
</style>


