<template>
    <div class="login-content">
        <div class="login-title">登录</div>
        <div class="login-body">
            <div>
                <span>账号:</span>
                <input type="text" placeholder="手机号" v-model="username" @blur="usernameBlur" @focus="usernameFocus">
            </div>
            <div class="error-text"><span v-show="usernameError">账号不正确</span></div>
            <div>
                <span>密码:</span>
                <input type="password" v-model="password" @blur="passwordBlur" @focus="passwordFocus">
            </div>
            <div class="error-text"><span v-show="passwordError">密码不正确</span></div>
            <div>
                <button class="login-btn" type="button" @click="login" :disabled="buttonDisabled">登录</button>
            </div>
        </div>
        <div class="login-footer">
            <div class="footer-text"><a href="#">忘记密码？</a></div>
        </div>
    </div>
</template>


<script>
    export default {
       data (){
           return {
               username: '',
               password: '',
               usernameError: false,
               passwordError: false,
               buttonDisabled: true,
               usernamestatus: false,
               passwordStatus: false,
           }
       },
        methods: {
            login (){
                //登录方法
            },
            usernameBlur (){
                //用户名失去焦点:
                let pattern = /^1\d{10}$/;
                if(pattern.test(this.username)){
                    
                }else{
                    this.usernameError = true;
                }
            },
            passwordBlur (){
                //password失去焦点
                if(this.password.length < 6){
                    this.passwordError = true;
                }
            },
            usernameFocus (){
                //账号获得焦点
                this.usernamestatus = false;
                this.buttonDisabled = true;
                this.usernameError = false;
            },
            passwordFocus (){
                //密码获得焦点
                this.passwordStatus = false;
                this.buttonDisabled = true;
                this.passwordError = false;
            }
        },
        watch: {
            usernamestatus (){
                if(!this.usernamestatus && !this.passwordStatus){
                    this.buttonDiaabled = false; 
                    this.passwordError = false;
        
                }
            },
            passwordStatus (){
                if(!this.usernamestatus && !this.passwordStatus){
                    this.buttonDiaabled = false;
                }
            }
        }
    }
</script>

<style scoped>
    .login-title {
        background-color: #07a81d;
        color: #ededed;
        font-size: 24px;
        text-align: center;
        padding: 10px 0;
    }
    .login-body {
        margin-top: 40px;
        font-size: 20px;
        color: #5e5d5d;
        text-align: center;
    }
    .login-content {
        background-color: #e1e0e0;
    }
    input {
        line-height: 40px;
        border: none;
        border-radius: 5px;
        font-size: 20px;
    }
    .error-text {
        font-size: 16px;
        color: #ff0000;
        padding-bottom: 30px;
    }
    button {
        width: 150px;
        background-color:#07a81d;
        border-radius: 5px;
        font-size: 28px;
        color: #fff;
        box-shadow: none;
        outline: none;
        border: none;
    }
    .footer-text {
        text-align: right;
        margin-right: 20px;
        padding-bottom: 20px;
    }
    .footer-text a {
        text-decoration: none;
        color: #808080;
    }
</style>