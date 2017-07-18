<template>
    <div class="print-file">
       <div>
           <print-title :nowIndex="1"></print-title>
       </div>
       <div class="print-file-infos">
           <div class="left infoes">
               <upload></upload>
               <seller-detail></seller-detail>
               <price-list></price-list>
           </div>
           <div class="right">
               右边
           </div>
       </div>
    </div>    
</template>


<script>
    import PrintTitle from '../components/base/PrintTitle'
    import Upload from '../components/base/Upload'
    import SellerDetail from '../components/base/SellerDetail'
    import PriceList from '../components/base/PriceList'
    
    export default {
        props: {
            
        },
        components: {
            PrintTitle,
            Upload,
            SellerDetail,
            PriceList
        },
        data (){
            return {
                
            }
        },
        methods: {
            
        }
    }

</script>

<style>
    .infoes {
        margin-top: 30px;
        width: 270px;
    }
    .print-file-infos {
        height: 800px;
    }
</style>
