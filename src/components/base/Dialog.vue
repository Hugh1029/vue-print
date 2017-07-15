<template>
    <div>
        <div class="dialog">
           <div class="dialog-cover" v-if="isShowDialog" @click="closeDialog"></div>
               <transition name="fade">
                   <div class="dialog-content" v-if="isShowDialog">
                       <p class="dialog-close" @click="closeDialog"></p>
                       <slot>content</slot>
                   </div>
               </transition>
        </div>
    </div>
</template>



<script>
    export default {
        props: {
            isShowDialog: {
                type: Boolean,
                default: false
            }
        },
        data (){
            return {
                
            }
        },
        methods: {
            closeDialog (){
                this.$emit('on-close')
            }
        }
    }

</script>


<style scoped>
    .fade-enter-active {
        transition: all .5s ease;
    }
    .fade-enter {
        transform: translateY(-500px);
    }
    .fade-leave-active {
        transition: all .3s ease;
    }
    .fade-leave {
        transform: translateY(-500px);
    }
    .dialog {
        position: fixed;
        width: 100%;
        height: 100%;
    }
    
    .dialog-cover {
        background: #000;
        opacity: .3;
        position: fixed;
        z-index: 10;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
    }
    
    .dialog-content {
        width: 50%;
        position: fixed;
        max-height: 50%;
        overflow: auto;
        background: #fff;
        top: 20%;
        left: 50%;
        margin-left: -25%;
        z-index: 15;
        border-radius: 5px;
        
    }
    
    .dialog-close {
        position: absolute;
        right: 5px;
        top: 5px;
        width: 20px;
        height: 20px;
        text-align: center;
        cursor: pointer;
    }
    .dialog-close:hover {
        color: #4fc08d;
    }

</style>