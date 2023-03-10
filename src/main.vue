<script>
import Home from './components/Home.vue'
import File from './components/File.vue'
const routes = {
    '/': Home,
    '/file': File
}
export default {
    data () {
        return {
            activeName: '',
            currentPath: window.location.hash
        }
    },
    computed: {
        currentTab() {
            // return this.activeName === 'home' ? 'Home' : 'File'
            console.log('current path ', this.currentPath)
            return routes[this.currentPath.slice(1) || '/']
        }
    },
    mounted() {
       window.addEventListener('hashchange', () => {
        this.currentPath = window.location.hash
       })
    },
    methods: {
        handleClick () {
            
        }
    }
}
</script>
<template>
<!--    <el-container style="height: 100%; width: 100%;">
         <el-header>
            <h3>后台管理系统</h3>
        </el-header>
        <el-main>
        </el-main>
   </el-container> -->
   <div>
<!--     <el-tabs v-model="activeName" @click="handleClick">
            <el-tab-pane label="主页" name="home">
                <component :is="currentTab"></component>
            </el-tab-pane>
            <el-tab-pane label="文件管理" name="file">
                <component :is="currentTab"></component>
            </el-tab-pane>
        </el-tabs> -->
        <a href="#/">主页</a>  |
        <a href="#/file">文件管理</a>
        <component :is="currentTab"></component>
   </div>
</template>
<style scoped>
</style>