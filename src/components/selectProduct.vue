<template>
    <div class="selectProduct">
        <div class="showSelected">
            <img class="showSelectedImg" src="../../static/img/product/main-1.jpg">
            <span>{{currency}}:{{price}}</span>
            <img class="exit" src="../../static/img/eixt.png">    
        </div>
        <div class="attr">
            <p class="attrTitle">{{attrTitle}} :</p>
            <p>
                <span>Pink</span>
                <span>Blue</span>
                <span>Green</span>
            </p>
        </div>
        <div class="quantity clear">
            Quantity :
            <div class="selectNum rt">
                <span>-</span>
                <input type="text">
                <span>+</span>
            </div>
        </div>
        <div class="submitButton">Submit</div>
    </div>
</template>

<script>
export default {
    name: 'selectProduct',
    data () {
        return {
            currency: 'RM',
            price: '169',
            attrTitle: 'Color'
        }
    }
}
</script>
<style scoped>
@import '../../static/css/base.css';
.selectProduct{
    background: #fff;
    border-radius: 20px;
    box-shadow: 0px 0px 5px #ccc;
    position: absolute;
    box-sizing: border-box;
    bottom: 0;
    width: 100%;
}
.showSelected,.attr{
    border-bottom: 1px solid #ddd;
    padding: 5px;
}
.showSelected span{ font-size: 1.2em;}
.showSelectedImg{
    width: 20%;
    vertical-align: middle;
    margin-right: 10px;
}
.attrTitle{
    color: #999;
    font-size: 1em;
    margin-bottom: 5px;
}
.attr{
    padding: 10px;
}
.attr p span {
    background: #ddd;
    color: #000;
    padding: 2px 10px;
    border-radius: 5px;
}
.attr p span:hover {
    background: #eb4012;
    color: #fff;
}
.quantity{
    font-size: 1.6em;
    padding: 10px;
}
.selectNum span{
    font-size: 1.4em;
    vertical-align: middle;
}
.selectNum input{
    width: 60px;
    height: 30px;
    text-align: center;
}
</style>


