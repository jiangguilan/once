<template>
    <div class="userMsg">
        <div class="showProductMsg">
            <img class="productImg" src="../../static/img/product/main-1.jpg">
            <div class="productMsg">
                <p>{{currency}} : {{price}}</p>
                <span>{{productTitle}}</span>
            </div>
            <img class="exit" src="../../static/img/eixt.png">
        </div>
        <div class="userMSg">
            <div>
                <span>
                    Full Name : 
                    <span>*</span>
                </span>
                <input type="text" placeholder="Please enter the full name">
            </div>
            <div>
                <span>
                    Phone number (+60) : 
                    <span>*</span>
                </span>
                <input type="text" placeholder="Please enter the phone number">
            </div>
            <div>
                <span>
                    Address : 
                    <span>*</span>
                </span>
                <input type="text" placeholder="Please enter the address">
            </div>
            <div>
                <span>State :</span>
                <select name="" id="">
                    <option value="0">Perlis</option>
                </select>
            </div>
            <div>
                <span>City :</span>
                <select name="" id="">
                    <option value="0">Arua</option>
                </select>
            </div>
            <div>
                <span>
                    Post code : 
                    <span>*</span>
                </span>
                <input type="text" placeholder="Please enter the post code">
            </div>
            <div>
                <span>Email : </span>
                <input type="text" placeholder="Please enter the email">
            </div>
            <div>
                <span>Order Notes : </span>
                <input type="text" placeholder="Please enter the order notes">
            </div>
        </div>
        <div class="orderMsg">
            <div class="clear">
                <span class="lt">Total Amount :</span>
                <span class="rt msg">{{currency}} : {{price}}</span>
            </div>
            <div class="clear">
                <span class="lt">Shipping Fee :</span>
                <span class="rt msg">Free Shipping</span>
            </div>
            <div class="clear">
                <span class="lt">Payment Method :</span>
                <span class="rt msg">Cash On Delivery
                    <img src="../../static/img/car.png">
                </span>
            </div>
        </div>
        <div class="submitButton">Complete Order</div>
    </div>
</template>

<script>
export default {
    name: 'userMsg',
    data () {
        return {
            currency: 'RM',
            price: '199',
            productTitle: '500ml Portable Juicer Bottle USB Rechargeable Electric Smoothie Maker Blender Bingo Vegetables Fruit Juice Blender Mixer Bottle '
        }
    }
}
</script>
<style scoped>
@import '../../static/css/base.css';
.userMsg{
    background: #fff;
    width: 100%;
    border-radius: 20px;
    box-shadow: 0px 0px 5px #ccc;
}
.showProductMsg{
    position: relative;
    padding: 5px;
    font-size: 1.2em;
}
.productImg{
    width: 20%;
    vertical-align: baseline;
    margin-right: 10px;
}
.productMsg{
    display: inline-block;
    width: 70%;
}
.userMSg div{
    margin: 10px 0px;
    padding: 0px 10px ;
    box-sizing: border-box;
}
.userMSg div{
    border-bottom: 1px solid #ddd;
}
.userMSg div input,.userMSg div select{
    width: 68%;
    height: 30px;
    font-size: 1.3em;
    border: none;
    outline: none;
}
.userMSg div span{
    display: inline-block;
    width: 30%;
    height: 30px;
    color: rgb(82, 82, 82);
    font-size: 1em;
}
.userMSg div span span{
    color: red;
    display: inline;
}
.orderMsg{
    padding: 10px;
}
.orderMsg div span{
    font-size: 1em;
}
.orderMsg div span.msg{
    color: #eb4012;
}
</style>

