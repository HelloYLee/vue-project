<script>
import axios from 'axios'

// Vue.prototype.$ajax = axios

export default {
    data () {
        return {

        }
    },
    mounted() {
        axios({
            method: 'get',
            url: 'src/assets/info.json'  //请求本地文件
            // url: 'http://localhost:5173/src/assets/info.json'
        }).then(res => {
            console.log(res)
        })
    }
}
</script>
<template>
    <el-container>
        <el-header>
           <h4>欢迎来到我的主页</h4>
        </el-header>
        <el-main>
           
        </el-main>
    </el-container>
</template>
<style>
</style>