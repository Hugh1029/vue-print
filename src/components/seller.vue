<template>
   <div>
       <div class="sellerInfo left" @mouseover="showHidden" @mouseout="hiddenInfo">
            <div class="seller-bg">
                <div class="sellerStatus" v-if="sellerStatus">正常营业</div>
                <div class="sellerStatusFalse" v-if="!sellerStatus">暂停营业</div>
            </div>
            <div class="seller-content">
                <div class="seller-title">{{sellername}}</div>
                <div class="seller-line">
                    <span class="left">价格:{{price.sba4}}</span>
                    <span class="right margin-right">评价:暂无评价</span>
                </div>
                <div class="seller-line">
                    <span class="left">营业时间:{{sellerTime}}</span>
                    <span class="right margin-right">起印张数:{{count}}张</span>
                </div>
                <div class="seller-line">
                    <span class="left">配送费:{{deliverMoney}}元</span>
                </div>
                <div class="seller-line center">
                    <span class="blue-border">配送时间:{{deliverTime}}分钟</span>
                </div>
            </div>
            <div class="seller-hidden-info" :class="{hidden:isShowHidden}">
                <div class="hidden-title">
                    {{sellername}}
                    <span class="blue-text">证</span>
                </div>
                <div>
                    <img src="../assets/pic-01.jpg">
                </div>
                <div class="hidden-text">
                    地址:{{sellerAddress}}
                </div>
                <div class="hidden-text">
                    电话:{{telephone}}
                </div>
                <div class="line"></div>
                <div class="price-title">价格列表</div>
                <div>
                    <span class="left-text">单面黑白A4:{{price.sba4}}</span>
                    <span class="right-text">双面黑白A4:{{price.dba4}}</span>
                </div>
                <div>
                    <span class="left-text">单面彩色A4:{{price.sca4}}</span>
                    <span class="right-text">双面彩色A4:{{price.dca4}}</span>
                </div>
                <div>
                    <span class="left-text">单面黑白A3:{{price.sba3}}</span>
                    <span class="right-text">双面面黑白A3:{{price.dba3}}</span>
                </div>
                <div>
                    <span class="left-text">单面彩色A3:{{price.sca3}}</span>
                    <span class="right-text">双面彩色A3:{{price.dca3}}</span>
                </div>
                <div class="line"></div>
                <div>店铺公告</div>
                <div class="report-text">
                <p>{{report}}</p>
                </div>
            </div>
        </div>
        
   </div>
</template>

<script>
    export default {
        props: {
            shopId: {
              type: String,
              default: '1245636'
            },
            sellername: {
                type: String,
                default: '亲打印文印店'
            },
            sellerStatus: {
                type: Boolean,
                default: true
            },
            sellerTime: {
                type: String,
                default: '08:00-21:00'
            },
            count: {
                type: Number,
                default: 0
            },
            deliverMoney: {
                type: Number,
                default: 0
            },
            deliverTime: {
                type: Number,
                default: 30
            },
            sellerAddress: {
                type: String,
                default: ''
            },
            price: {
                type: Object,
                default: function(){
                    return {
                        sba4: 0.1,
                        sba3: 0.8,
                        sca4: 0.8,
                        sca3: 1.5,
                        dba4: 1.5,
                        dba3: 1.2,
                        dca4: 1.5,
                        dca3: 2.5
                    }
                }
            },
            telephone: {
                type: String,
                default: '15366088228'
            },
            report: {
                type: String,
                default: '节假日不休息'
            }
        },
        data (){
            return {
                isShowHidden: true
            }
        },
        methods: {
            showHidden (){
                this.isShowHidden = false
            },
            hiddenInfo (){
                this.isShowHidden = true
            }
        }
    }
</script>

<style>
    .sellerInfo {
        background-color: #e8e9ed;
        width: 250px;
        height: 400px;
        text-align: center;
        position: relative;
        margin-right: 50px;
        margin-bottom: 50px;
    }
    .seller-bg {
        background: url(../assets/shop-pic.png) no-repeat;
        width: 230px;
        height: 210px;
        margin: auto;
        cursor: pointer;
     }
    .seller-content {
        margin-top: 15px;
        letter-spacing: 1px;
    }
    .seller-title {
        margin-bottom: 10px;
        font-weight: bold;
    }
    .half {
        
    }
    .seller-line {
        width: 100%;
        text-align: left;
        font-size: 12px;
        padding: 12px;
    }
    .margin-right {
        margin-right: 20px;
    }
    .center {
        text-align: center;
    }
    .blue-border {
        border: 1px solid #00a8ff;
        color: #00a8ff;
        padding: 2px 5px;
        border-radius: 4px;
    }
    .blue-text {
        border: 1px solid #00a8ff;
        color: #00a8ff;
        padding: 0 2px;
        font-size: 12px;
        border-radius: 3px;
    }
    .sellerStatus {
        color: #e8e9ed;
        position: relative;
        top: 120px;
        font-size: 18px;
        font-weight: bold;
    }
    .sellerStatusFalse {
        color: #a3a4a6;
        position: relative;
        top: 120px;
        font-size: 18px;
        font-weight: bold;
    }
    
    .seller-hidden-info {
        border: 1px solid #808080;
        width: 250px;
        height: 400px;
        position: absolute;
        top: 0;
        left: 250px;
        overflow: hidden;
        z-index: 50;
        background-color: #fff;
    }
    .hidden-title {
        margin-top: 20px;
        text-align: left;
        font-weight: bold;
        color: #313132;
        padding-left: 20px;
        margin-bottom: 15px;
    }
    .line {
        background-color: #edeef2;
        height: 1px;
        width: 230px;
        margin: 8px 10px;
    }
    .hidden-text {
        font-size: 12px;
        color: #808080;
        padding: 3px 20px 1px;
        text-align: left;
        overflow: hidden;
    }
    .price-list {
        font-size: 12px;
        width: 240px;
        text-align: left;
    }
    .left-text {
        font-size: 12px;
        color: #808080;
        width: 50%;
        margin: 20px;
    }
    .right-text {
        font-size: 12px;
        color: #808080;
        width: 50%;
        margin: 20px;
    }
    .price-title {
        color: #ff0000;
        margin-bottom: 5px;
    }
    .report-text {
        font-size: 12px;
        color: #808080;
        text-align: left;
        margin: 0 15px;
        overflow: hidden;
    }
    .report-text p {
        margin: 0;
        padding: 0;
    }
    .hidden {
        display: none;
    }
</style>
