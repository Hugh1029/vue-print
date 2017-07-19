<template>
    <div class="selector">
        <select v-model="selectValue">
            <option v-for="list in options" :value="list.value">{{list.item}}</option>
        </select>
    </div>
</template>
<script>
    export default {
        props: {
            selectIndex: Number,
            options: {
                type: Array,
                default: function (){
                    return [
                        {
                            item: '不缩印',
                            value: '1'
                        }
                    ]
                }
            }
        },
        data (){
            return {
                selectValue: this.options[0].value
            }
        },
        watch: {
            selectValue (){
                this.$emit('selchange',this.selectIndex,this.selectValue);
            }
        }
    }
</script>


<style scoped>
    .selector {
        display: inline-block;
    }
</style>