<template>
    <div class="seller-body">
       <div class="seller-body-title">店铺信息</div>
       <div class="seller-body-tip"></div>
       <div class="seller-content">
           <div class="info-title">店铺名:</div>
           <div class="info-content">{{sellers.sellerName}}</div>
           <div class="info-title">店铺地址:</div>
           <div class="info-content"><p>{{sellers.sellerAddress}}</p></div>
           <div class="info-title">联系方式:</div>
           <div class="info-content">{{sellers.telephone}}</div>
       </div>
    </div>
</template>
<script>
    export default {
        props: {
            sellers: {
                type: Object,
                default: function(){
                    return {
                        sellerName: '今天睡不着啊',
                        sellerAddress: '汇金新天地对不对啊',
                        telephone: '15366088888'
                    }
                }
            }
        },
        data (){
            return {
                
            }
        },
        methods: {
            
        }
    }
</script>


<style scoped>
    .seller-body {
        border: 1px solid #a5a1a1;
        margin-bottom: 30px;
        padding-bottom: 20px;
    }
    
    .seller-body-title {
        color: #fff;
        background-color: #07a81d;
        width: 80px;
        padding: 5px 0 5px 10px;
    }
    .seller-body-tip {
        background-color: #07a81d;
        width: 5px;
        height: 30px;
    }
    .info-title {
        font-size: 14px;
        font-weight: bold;
    }
    .info-content {
        font-size: 12px;
        padding: 4px 0;
    }
    .info-content p {
        margin: 0;
        padding: 0;
    }
    .seller-content {
        padding-left: 10px;
    }
</style>