<template>
    <div class="print-file">
       <div>
           <print-title :nowIndex="1"></print-title>
       </div>
       <div class="print-file-infos">
           <div class="left infoes">
               <upload @addfile='addFile'></upload>
               <seller-detail></seller-detail>
               <price-list :priceList="pricelist"></price-list>
           </div>
           <div class="right file-infos">
               <file-list :fileLists="fileLists"></file-list>
           </div>
       </div>
    </div>    
</template>


<script>
    import PrintTitle from '../components/base/PrintTitle'
    import Upload from '../components/base/Upload'
    import SellerDetail from '../components/base/SellerDetail'
    import PriceList from '../components/base/PriceList'
    import FileList from '../components/FileList'
    
    export default {
        props: {
            
        },
        components: {
            PrintTitle,
            Upload,
            SellerDetail,
            PriceList,
            FileList
        },
        data (){
            return {
                fileLists: [],
                pricelist: [
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
        },
        methods: {
            addFile (fileInfo){
                var file = {
                    filename: fileInfo.filename,
                    fileId: fileInfo.fileId,
                    pages: fileInfo.pages
                }
                this.fileLists.push(file)
            }
        },
        watch: {
            fileLists (){
                console.log(this.fileLists);
            }
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
    
    .file-infos {
        margin-top: 30px;
        
    }
</style>
