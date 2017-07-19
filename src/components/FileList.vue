<template>
    <div class="file-list">
        <div v-for="(list,index) in fileLists">
            <div>{{list.filename}}</div>
            <selector :options="fileStyle" :selectIndex="index" @selchange="changeFileStyle"></selector>
            <selector :options="double" :selectIndex="index" @selchange="changeDouble"></selector>
            <selector :options="color" :selectIndex="index" @selchange="changeColor"></selector>
            <selector :options="fileSize" :selectIndex="index" @selchange="changeFileSize"></selector>
            <span>{{list.pages}}</span>
            <counter :countIndex="index" @countchange='changecount'></counter>
            <span>{{price(index)}}</span>
        </div>
    </div>    
</template>


<script>
    import Counter from './base/Counter'
    import Selector from './base/Selector'
    export default {
        props: {
            fileLists:{
                type: Array
            }
        },
        components: {
            Counter,
            Selector
        },
        data (){
            return {
                fileStyle:[
                    {
                        item: '不缩印',
                        value: '1'
                    },
                    {
                        item: '一页两版',
                        value: '2'
                    },
                    {
                        item: '一页四版',
                        value: '4'
                    },
                    {
                        item: '一页六版',
                        value: '6'
                    },
                    {
                        item: '一页九版',
                        value: '9'
                    }
                ],
                color: [
                    {
                        item: '黑白',
                        value: '黑白'
                    },
                    {
                        item: '彩色',
                        value: '彩色'
                    }
                ],
                double: [
                    {
                        item: '单面',
                        value: '单面'
                    },
                    {
                        item: '双面',
                        value: '双面'
                    }
                ],
                fileSize: [
                    {
                        item: 'A4',
                        value: 'A4'
                    },
                    {
                        item: 'A5',
                        value: 'A5'
                    }
                ]
                
            }
        },
        methods: {
            changecount (count,index){
                this.fileLists[index].count = count;
            },
            changeFileStyle (index,value){
                this.fileLists[index].fileStyle = value;
                console.log(this.fileLists[index]);
            },
            changeDouble (index,value){
                console.log(index);
                console.log(value);
                this.fileLists[index].double = value;
            },
            changeColor (index,value){
                this.fileLists[index].color = value;
            },
            changeFileSize (index,value){
                this.fileLists[index].fileSize = value;
            },
            price (index){
               console.log(this.fileLists);
                /*var fileArgs = this.fileLists[index].color + this.fileLists[index].double + this.fileLists[index].color;
                console.log(this.fileLists[index].color);
                return fileArgs;*/
            }
        },
        computed: {
            
        }
    }
</script>

<style scoped>
    .file-list {
        border: 1px solid #a5a1a1;
        width: 750px;
        min-height: 650px;
    }
</style>