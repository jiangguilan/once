<template>
    <div class="container">
        <!-- <div class="banner"></div> -->
        <banner/>
        <div class="fixedTitle">
            <div>
                <p>
                    <span>RM:169</span>
                    <span>RM:399</span>
                </p>
                <p>
                    <span><img src="">Flash deals</span>
                    <span>80%</span>
                </p>
            </div>
            <div>
                <p>Ends In</p>
                <p>00:00:00</p>
            </div>
        </div>
        <div class="soldProduct"></div>
        <div class="productTitle"></div>
        <div class="guarantee"></div>
        <!-- <div class="reviewNum"></div>
        <div class="reviewMsg"></div> -->
        <review/>
        <!-- <div class="productDetail"></div> -->
        <productDetail/>
        <!-- <div class="vedio"></div> -->
        <vedio/>
        <div class="purchaseGuide"></div>
        <div class="buyNow">
            <button>Buy Now</button>
        </div>
        <!-- <div class="selectProduct"></div> -->
        <selectProduct/>
        <!-- <div class="userMsg"></div> -->
        <userMsg/>
        <!-- <div class="complete"></div> -->
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
            msg: 'hello index page'
        }
    },
    