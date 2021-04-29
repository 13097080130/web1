<template>
    <div id="loginWrapper">
        <div id="loginConter">
            <el-card class="box-card">
                <div slot="header" class="clearfix">
                <span>登录系统</span>
                <el-button style="float: right; padding: 3px 0" type="text">忘记密码</el-button>
                </div>
                <div id="loginContmentbody">
                    <el-input id="username" v-model="user.username"  clearable></el-input>
                    <el-input id="password" v-model="user.password" show-password clearable></el-input>
                </div>
                <div id="loginSubmit">
                    <el-button id="SystemSubmit" @click="loginSystem">登录</el-button>
                </div>
            </el-card>  
        </div>
    </div>
</template>

<script>
import Axios from 'axios'
export default {
    data(){
        return{
            user:{
                username:"",
                password:""
            }
        }
    },
    methods:{
        loginSystem(){
            Axios.get('http://localhost:3000/login').then(function(response){
                alert(response.data)
            })
        }
    }
}
</script>

<style>

#loginWrapper{
    height: 100%;
    /* background-color: antiquewhite; */
}  
#loginConter{
    width: 400px;
    margin: auto;
    padding: 100px;

} 
/* input中间空隙 */
#loginContmentbody>*{
    margin: 5px;
}

#loginSubmit{
    display: block;
    text-align: center;
}
#SystemSubmit{
    display: block;
    margin: auto;
    background-color: #0a9588;
    color: white;
    border-color: #0a9588;
} 
</style>