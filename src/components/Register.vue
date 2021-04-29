<template>
    <div id="loginWrapper">
        <div id="loginConter">
            <el-card class="box-card">
                <div slot="header" class="clearfix">
                <span>用户注册</span>
                <el-button style="float: right; padding: 3px 0" type="text">忘记密码</el-button>
                </div>
                <div id="loginContmentbody">
                    <el-input id="newusername" v-model="newuser.newusername"  clearable></el-input>
                    <el-input id="newpassword" v-model="newuser.newpassword" show-password clearable></el-input>
                </div>
                <div id="loginSubmit">
                    <el-button id="SystemSubmit" @click="registerSystem">注册</el-button>
                </div>
            </el-card>  
        </div>
    </div>
</template>

<script>
import Axios from 'axios'
export default {
    name:"register",
    data(){
        return{
            newuser:{
                newusername:"",
                newpassword:""
            }
        }
    },
    methods:{
        registerSystem(){
            Axios.get('http://localhost:3000/register',{
                params:this.newuser
            }).then(function(response){
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