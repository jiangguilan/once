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
                        <span>80%</span> 
                    </span>
                </p>
            </div>
            <div class="timeDown rt">
                <p>Ends In</p>
                <p class="downTime">
                    <span>00</span> :
                    <span>00</span> :
                    <span>00</span>
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
        <div class="buyNow submitButton">Buy Now</div>
        <selectProduct/>
        <userMsg/>
        <complete/>
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
            productTitle: 'Hurricane Spin Duster'
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
    created: function () {
        //在一个实例被创建之后执行代码
    },
    mounted: function () {

    },
    updated: function ()  {

    },
    destroyed: function () {
        
    }
}
</script>
<style>
@import '../../static/css/base.css';
@import '../../static/css/index.css';
</style>


