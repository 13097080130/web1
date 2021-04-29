<template>
  <div id="app">
    <!-- 3，使用子组件 -->
    <el-container>
      <el-header id="herderBook">
        <Herder/>
      </el-header>
      <el-main id="mainBook">
        <!-- <login/> -->
        <router-view></router-view>
      </el-main>
      <el-footer id="footerBook">
        <Footer/>
      </el-footer>
    </el-container>  
  </div>
</template>

<script>
// 1，导入herder子组件
import Herder from "./components/Header.vue"
import login from "./components/login.vue"
import Footer from "./components/Footer"
// 2，注册 子组件
export default {
  name: 'App',
  components: {
    Herder,login,Footer
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  /* margin-top: 60px; */
}
#herderBook{
  background-color:#244152;
}
#mainBook{
  /* background-color: blue; */
  height: 500px;
}
#footerBook{
  /* background-color: green; */
  height: 150px  !important;
}
</style>
