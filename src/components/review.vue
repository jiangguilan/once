<template>
    <div class="review">
        <div class="reviewNum">Reviews({{reviewNum}})</div>
        <ul>
            <li>
                <div class="clear">
                    <p class="lt">
                        <img src="../../static/img/star_active.png">
                        <img src="../../static/img/star_active.png">
                        <img src="../../static/img/star_active.png">
                        <img src="../../static/img/star_active.png">
                        <img src="../../static/img/star_active.png">
                    </p>
                    <p class="rt">{{reviewUserName}}</p>
                </div>
                <div class="clear">
                    <p class="reviewMsg">{{reviewMsg}}</p>
                    <img class="lt reviewImg" src="../../static/img/product/review-1.png">
                    <span class="rt">{{reviewTime}}</span>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    name:'firstPage',
    data(){
        return{
            reviewNum: 754,
            reviewUserName: "Diane",
            reviewMsg: 'I am now cleaning, without any exertion, places and things that haven\'t been touched for a long time. Definitely recommend this!',
            reviewTime: '2018/7/18'
        }
    }
}
</script>
<style scoped>
@import '../../static/css/base.css';
.review{
    margin-top: 5px;
}
.reviewNum{
    background: #fff;
    color: #999;
    font-size: 1.5em;
    padding: 10px;
    margin: 5px 0px;
}
ul li {
    background: #fff;
    padding: 10px;
    box-sizing: border-box;
    margin-top: 5px;
    color: #999;
}
ul li .reviewImg{
    width: 30%;
}
.reviewMsg{
    color: #000;
    font-size: 1.2em;
}
</style>

