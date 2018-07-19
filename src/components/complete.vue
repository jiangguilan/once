<template>
    <div class="complete">
        <div class="title">Congrats!</div>
        <div>
            <p>Your order with us is submitted.</p>
            <p>An order confirmation email will be sent to your email address and our customer service team will reach out to you to schedule a delivery date.</p>
            <p>Your order number: <span class="highLight">{{orderNumber}}</span></p>
            <p>Grand Total: 
                <span class="highLight">{{currency}} :</span> 
                <span class="highLight">{{totalPrice}}</span>
            </p>
            <p>For customer service please contact : 
                <a href="mailto:support@arterest.com">support@arterest.com</a>
            </p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'complete',
    data () {
        return {
            currency: 'RM',
            totalPrice: 169,
            orderNumber: 'art2018071905422507'
        }
    }
}
</script>
<style scoped>
.complete{
    width: 100%;
    height: 100%;
    border-radius: 20px;
    box-shadow: 0px 0px 5px #ccc;
    background: #fff;
    padding: 10px;
    box-sizing: border-box;
}
.title{
    text-align: center;
    font-size: 2em;
}
.complete div p{
    font-size: 1.5em;
}
.highLight{
    color: #eb4012;
}
</style>


