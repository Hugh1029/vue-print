<template>
   <div class="uploadBody">
      <div class="upload-title">上传文件</div>
      <div class="upload-tip"></div>
      <div class="upload-com">
          <img src="../../assets/upload.png">
          <button class="uploadButton" @click="upload">点击上传</button>
      </div>
   </div>
    
</template>


<script>
    export default {
        props:{
            uploadType: {
                type: Array,
                default: function(){
                    return ['pdf','doc']
                }
            }
        },
        data (){
            return {
               fileInfo: {} 
            }
        },
        methods: {
            upload (){
                this.fileInfo = {
                    filename: '样本文件名称',
                    pages: 10,
                    fileId: '10001',
                    fileStyle: '',
                    fileSize: '',
                    color: '',
                    double: '',
                    price: 0,
                    count: 1
                }
                this.$emit('addfile',this.fileInfo);
            }
        }
    }
</script>



<style scoped>
    .uploadBody {
        border: 1px solid #a5a1a1;
        margin-bottom: 30px;
    }
    
    .upload-tip {
        background-color: #07a81d;
        width: 5px;
        height: 30px;
    }
    
    .upload-title {
        color: #fff;
        background-color: #07a81d;
        width: 80px;
        padding: 5px 0 5px 10px;
    }
    
    .upload-com {
        text-align: center;
        margin-top: 10px;
        margin-bottom: 10px;
    }
    .uploadButton {
        display: block;
        margin: 10px auto 40px;
        background-color: #07a81d;
        border: none;
        border-radius: 15px;
        color: #fff;
        padding: 5px 10px;
        font-size: 16px;
    }
</style>