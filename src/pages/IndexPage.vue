<template>
    <div>
        <seller v-for="(shop,index) in shopInfoList" :shopId="shop.shopId" :sellername="shop.shopName" :count="shop.count" :deliverTime="shop.deliverTime" :deliverMoney="shop.deliverMoney" :sellerStats="shop.sellerShopStatus" :sellerTime="shop.sellerTime" :sellerAddress="shop.sellerAddress" :telephone="shop.telephone" :report="shop.report" :price="shop.price" ></seller>
    </div>
</template>

<script>
    import Seller from '../components/seller'
    export default {
        props: {
            
        },
        components: {
            Seller
        },
        data (){
            return {
                shopInfoList:[
                    {
                        shopId: '123456',
                        shopName: '汇金图文店',
                        count: 500,
                        deliverMoney: 2,
                        deliverTime: 40,
                        sellerStatus: true,
                        sellerTime: '08:00-22:00',
                        sellerAddress: '汇金新天地',
                        telephone: '15366088888',
                        report: '每天都不休息，每天都配送',
                        price: {
                            sba4: 0.1,
                            sba3: 0.8,
                            sca4: 0.8,
                            sca3: 1.5,
                            dba4: 1.5,
                            dba3: 1.2,
                            dca4: 1.5,
                            dca3: 2.5
                        }
                    },
                     {
                        shopId: '123456',
                        shopName: '汇金图文店',
                        count: 500,
                        deliverMoney: 2,
                        deliverTime: 40,
                        sellerStatus: true,
                        sellerTime: '08:00-22:00',
                        sellerAddress: '汇金新天地',
                        telephone: '15366088888',
                        report: '每天都不休息，每天都配送',
                        price: {
                            sba4: 0.1,
                            sba3: 0.8,
                            sca4: 0.8,
                            sca3: 1.5,
                            dba4: 1.5,
                            dba3: 1.2,
                            dca4: 1.5,
                            dca3: 2.5
                        }
                    },
                     {
                        shopId: '123456',
                        shopName: '汇金图文店',
                        count: 500,
                        deliverMoney: 2,
                        deliverTime: 40,
                        sellerStatus: true,
                        sellerTime: '08:00-22:00',
                        sellerAddress: '汇金新天地',
                        telephone: '15366088888',
                        report: '每天都不休息，每天都配送',
                        price: {
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
                ]
            }
        },
        methods: {
            
        }
        
    }
</script>

<style>
    
</style>
