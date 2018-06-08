<template>
    <nav class="navbar">
        <div>RESUMEEDITOR</div>
        <ul>
            <el-row>
                <el-button type="primary" plain>注册</el-button>
                <el-button type="primary" plain>登录</el-button>                
            </el-row>   
            </ul>        
        </nav>
</template>

<script>
export default {
    name: 'topbar',
}
</script>

<style lang="scss" scoped>
.navbar{
    background-color: lightseagreen;
    display: flex;
    padding: 10px;
    justify-content: space-between;
    align-items: center;
    min-height: 46px;
    box-shadow: 0px 4px 8px 0px rgba(144,215,239,0.75);
    div{
        color: lightblue;
        font-size: 24px;
    }
    ul{
        margin: 0;
    }
}
</style>

