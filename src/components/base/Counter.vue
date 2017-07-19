<template>
    <div class="counter">
        <button type="button" @click='decrease'>-</button><input type="text" v-model="count"><button type="button" @click='increase'>+</button>
    </div>
</template>

<script>
    export default {
        
        props: {
            countIndex:{
                type: Number
            }
        },
        data (){
            return {
                count: 1
            }
        },
        methods: {
            decrease (){
                if(this.count > 1){
                    this.count --;
                }
            },
            increase (){
                this.count ++;
            }
        },
        watch: {
            count (){
                var pattern = /\d/;
                if(this.count < 1 || (!pattern.test(this.count))){
                    this.count = 1;
                }
                this.$emit('countchange',this.count,this.countIndex)
            }
        }
    }

</script>


<style scoped>
    .counter {
        display: inline-block;
    }
    .counter input {
        width: 30px;
        margin: 0 8px;
        text-align: center;
    }
    .counter a {
        font-size: 20px;
    }
</style>