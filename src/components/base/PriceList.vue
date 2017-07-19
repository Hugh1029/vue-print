<template>
    <div class="price-list">
      <div class="price-list-title">价格列表</div>
      <div class="price-list-tip"></div>
       <div class="pricelist-title"><span>打印类型</span><span>价格</span></div>
        <div v-for="(list,index) in priceList">
            <div class="price-content"><span>{{list.priceName}}:</span><span>{{list.price}}</span></div>
        </div>
    </div>
</template>

<script>

    export default {
        props: {
            priceList: {
                type: Array,
                default: function(){
                    return [
                        {
                            priceId: 1,
                            priceName: 'A4黑白单面',
                            price: 0.1
                        },
                        {
                            priceId: 2,
                            priceName: 'A4黑白双面',
                            price: 0.2
                        },
                        {
                            priceId: 3,
                            priceName: 'A3黑白单面',
                            price: 0.8
                        },
                        {
                            priceId: 4,
                            priceName: 'A3黑白双面',
                            price: 1.5
                        }
                    ]
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
    .price-list {
        text-align: center;
        border: 1px solid #a5a1a1;
    }
    .pricelist-title span {
        margin: 40px;
        font-weight: bold;
    }
    
    .price-list-title {
        color: #fff;
        background-color: #07a81d;
        width: 80px;
        padding: 5px 0 5px 10px;
    }
    .price-list-tip {
        background-color: #07a81d;
        width: 5px;
        height: 30px;
    }
    .price-content span {
        margin: 40px;
        font-size: 12px;
    }
    
</style>