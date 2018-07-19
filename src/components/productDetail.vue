<template>
    <div class="productDetail">
        <p>Product Details</p>
        <img src="../../static/img/product/detail-1.jpg">
    </div>
</template>

<script>
export default {
    name:'productDetail',
    data () {
        return {
            msg: 'this is productDetail'
        }
    }
}
</script>
<style scoped>
@import '../../static/css/base.css';
.productDetail{
    background: #fff;
    margin: 5px 0px;
}
.productDetail p{
    color: #999;
    font-size: 1.3em;
    padding: 10px;
} 
img{
    width: 100%;
}
</style>

