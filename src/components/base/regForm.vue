<template>
    <div class="regForm">
        <div class="reg-content">
            <div class="reg-title">注册</div>
            <div class="reg-body">
                <div class="body-line">
                    <label>手机号:</label>
                    <input type="text" v-model="username" @focus="focusVal(1)" @blur="blurVal(1)">
                </div>
                <div class="error-text"><p v-if="show1">请输入正确的手机号</p></div>
                <div class="val">
                    <span>获取动态验证码</span>
                </div>
                <div class="body-line">
                    <label>密码:</label>
                    <input type="password" v-model="password" @focus="focusVal(2)" @blur="blurVal(2)"> 
                </div>
                <div class="error-text"><p v-if="show2">密码格式不正确或长度不够</p></div>
                <div class="body-line">
                    <label>确认密码:</label>
                    <input type="password" v-model="surePassword" @focus="focusVal(3)" @blur="blurVal(3)">
                </div>
                <div class="error-text"><p v-if="show3">两次密码不一致</p></div>
                <div class="body-line center">
                    <button class="bak" type="button" @click="register" :disabled="buttonStatus" :class={isReg:buttonStatus}>注册</button>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
    export default {
        props: {
            
        },
        data (){
            return {
                username: '',
                password: '',
                surePassword: '',
                buttonStatus:true,
                show1: false,
                show2: false,
                show3: false
            }
        },
        methods: {
            register (){
                console.log("注册");
            },
            isButton (){
                if((this.show1 === false) && (this.show2 === false) && (this.show3 === false)){
                    this.buttonStatus = false;
                   }else {
                       this.buttonStatus = true;
                   }
            },
            focusVal (index){
                this.buttonStatus = true;
                switch(index){
                    case 1:
                        this.show1 = false;
                        break;
                    case 2:
                        this.show2 = false;
                        break;
                    case 3:
                        this.show3 = false;
                    default:
                        break;
                            }
            },
            blurVal (index){
                switch(index){
                    case 1: {
                        var pattern = /^1\d{10}$/;
                        if(!pattern.test(this.username)){
                            this.show1 = true;
                        }
                        this.isButton();
                        break;
                    }
                    case 2: {
                        if(this.password.length < 6){
                            this.show2 = true; 
                        }
                        this.isButton();
                        break;
                    }
                    case 3:
                        if(this.password !== this.surePassword){
                            this.show3 = true;
                        }
                        this.isButton();
                        break;
                    default:
                        break;
                            }
            }
            
        }
    }
</script>


<style scoped>
    .reg-content {
        background-color: #e1e0e0;
    }
    .reg-title {
        background: #07a81d;
        color: #fff;
        font-size: 24px;
        text-align: center;
        margin-bottom: 25px;
        padding: 5px;
    }
    .body-line {
        padding-top: 15px;
        text-align: right;
        
    }
    .reg-body {
        font-size: 14px;
    }
    
    
    .reg-body input {
        line-height: 24px;
        font-size: 28px;
        border: 1px solid #07a81d;
        border-radius: 5px;
        width: 280px;
        margin-right: 25%;
        margin-left: 10px;
        
    }
    
    .reg-body p {
        margin: 0;
        padding: 0;
    }
    .error-text {
        text-align: right;
        margin-right: 25%;
        color: #ff0000;
        font-size: 12px;
        padding-right: 10px;
    }
    
    .val {
        text-align: right;
        margin-right: 25%;
        font-size: 14px;
        padding-right: 10px;
        color: #3b3b3c;
    }
    .val span {
        background: #b2b2b3;
        border-radius: 5px;
    }
    
    .center {
        text-align: center;
    }
    .body-line button {
        border: none;
        color: #fff;
        width: 180px;
        height: 40px;
        border-radius: 8px;
        font-size: 20px;
        word-spacing: 5px;
        letter-spacing: 8px;
        margin-bottom: 40px;

    }
    .bak {
        background-color: #07a81d;
    }
    .isReg {
        background: #808080;
    }
</style>