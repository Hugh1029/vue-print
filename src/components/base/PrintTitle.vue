<template>
    <div class="print-title">
       <ul class="type-list">
           <li v-if="support.file">
              <router-link :to="{path:'/printFile'}">
               <div class="img-list" :class="{imglist: nowIndex==1}">
                   <img class="img" src="../../assets/upfiles_icon.png"/>
               </div>
               </router-link>
               <span>打印文件</span>
           </li>
           <li v-if="support.image">
               <div class="img-list" :class="{imglist: nowIndex==2}">
                   <img class="img" src="../../assets/photoprint_icon.png"/>
               </div>
               <span>打印照片</span>
           </li>
           <li v-if="support.binding">
               <div class="img-list" :class="{imglist: nowIndex==3}">
                   <img class="img" src="../../assets/photoprint_icon.png"/>
               </div>
               <span>胶装定制</span>
           </li>
           <li v-if="support.cd">
               <div class="img-list" :class="{imglist: nowIndex==4}">
                   <img class="img" src="../../assets/photoprint_icon.png"/>
               </div>
               <span>刻录光盘</span>
           </li>
       </ul>
    </div>
</template>

<script>
    
    export default {
        props: {
            nowIndex:{
                type: Number,
                default: 1
            },
            support: {
                type: Object,
                default: function(){
                    return {
                        file: true,
                        image: true,
                        binding: true,
                        cd: true
                    }
                }
            }
        },
        data (){
            return {
                aaa: true
            }
        }
        
    }
</script>


<style scoped>
    .print-title {
        border: 1px solid #a5a1a1;
        text-align: center;
        margin: auto;
    }
    .type-list {
        list-style: none;
    }
    .type-list li {
        display: inline-block;
        margin:auto 55px;
    }
    .img-list {
        background-color: #a5a1a1;
        border-radius: 50%;
        width: 96px;
        height: 96px;
        text-align: center;
        vertical-align: middle;
        padding: auto;
        cursor: pointer;
    }
    .img {
        width: 70px;
        height: 70px;
        margin-top: 10px;
    }
    .imglist {
        background-color: #0E92FF;
    }
    .type-list li span {
        font-size: 12px;
        font-weight: bold;
    }
</style>