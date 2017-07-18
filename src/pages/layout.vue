<template>
    <div class="container">
      <!--头部-->
       <div class="header">
           <div class="left">
              <div class="left-content">
                  <img class="logo" src="../assets/logo.png">
                  <img class="logo-text" src="../assets/bg.png">
                  <a class="index-address">金陵科技学院</a>
              </div>
           </div>
           <div class="nav right">
                   <ul>
                       <li @click="userLogin">登录</li>
                       <li @click="userReg">注册</li>
                       <li>个人中心</li>
                       <li>我是商家</li>
                   </ul>
           </div>
       </div>
       
       <!--中间部分-->
       <div class="content">
           <router-view></router-view>
       </div>
       
       <!--尾部-->
        <div class="footer">
            <div class="footer-left left">
               <ul>
                   <li>联系我们</li>
                   <li>QQ:2025225064</li>
                   <li>微信公众号：亲打印</li>
                   <li>加盟热线：15250970888</li>
                   <li>南京韵奇盈信息技术有限公司 版权所有</li>
                   <li>
                       <a href="http://www.miitbeian.gov.cn">苏ICP备16004057号-1</a>
                   </li>
               </ul>
            </div>
            <div class="footer-right right">
                <img class="wx" src="../assets/WX.jpg">
            </div>
        </div>
        <my-dialog :is-show-dialog="loginShow" @on-close="closeDialog('loginShow')">
            <login-form></login-form>
        </my-dialog>
        <my-dialog :is-show-dialog="regShow" @on-close="closeDialog('regShow')">
            <reg-form></reg-form>
        </my-dialog>
    </div>
</template>

<script>
    import Dialog from '../components/base/Dialog'
    import LoginForm from '../components/base/loginForm'
    import RegForm from '../components/base/regForm'
    export default {
        components: {
            MyDialog:Dialog,
            LoginForm,
            RegForm
        },
        data (){
            return {
                loginStatus: false,
                loginShow: false,
                regShow: false
            }
        },
        methods: {
            closeDialog (index){
                this[index]= false;
            },
            userLogin (){
                if(this.loginStatus){
                    this.loginStatus = false;
                }else{
                    this.loginShow = true;
                }
            },
            userReg (){
             this.regShow = true;   
            }
        }
    }
</script>


<style>
    body,html {
        margin: 0;
        padding: 0;
    }
    .left {
        float: left;
    }
    .right {
        float: right;
    }
    .inline {
        display: inline;
    }
    .container {
        width: 1080px;
        margin: auto;
    }
    .header {
        border: 1px solid #a5a1a1;
        border-top: 5px solid #b74812;
        height: 120px;
    }
    .logo {
        width: 96px;
    }
    .logo-text {
        width: 200px;
    }
    .left-content {
        vertical-align: middle;
    }
    .index-address{
        position: relative;
        font-size: 12px;
        left: -170px;
        top: 20px;
        color: #c1bdbd;
    }
    
    .nav ul{
        list-style: none;
    }
    .nav ul li {
        display: inline;
        margin: 10px;
        font-size: 14px;
        cursor: pointer;
        color: #a5a1a1;
    }
    .nav ul li:hover {
        color: #00ff18;
        font-weight: bold;
    }
    
    .content {
        min-height: 500px;
        margin: 30px 0;
        height: auto;
        display: block;
        
    }
    
    .footer {
        background-color: #07a81d;
        color: #efefef;
        height: 230px;
    }
    
    .footer-left ul {
        list-style: none;
    }
    
    .footer-left ul li {
        padding: 5px;
    }
    
    .footer-left {
        margin-left: 30px;
        margin-top: 10px;
    }
    
    .footer-left li a {
        text-decoration: none;
        color: #444;
    }
    .wx {
        width: 128px;
    }
    .footer-right {
        margin-right: 200px;
        margin-top: 50px;
    }
</style>