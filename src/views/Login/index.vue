<template>
    <div id="login">
        <div class="login-wrap">
            <ul class="menu-tab">
                <li v-for="(item) in menuTab" :key="item.id" :class="{'current':item.current}" @click="toggleMenu(item)">{{item.txt}} </li>
            </ul>     
        </div>   
    </div>
</template>
<script>
export default {
    name:"login",
    data(){
        return {
            menuTab:[
                {txt:"登录",current:false},
                {txt:"注册",current:false}
            ]
        }
    },
    // 写函数的地方
    methods: {
        toggleMenu(item){
            this.menuTab.forEach(element => {
                element.current = false;
            });
            item.current = true
        }
    }
}
</script>

<style lang="scss" scoped>
    #login{
        height: 100vh;
        background-color: #344a5f;
    }
    .login-warp{
        width:330px;
        margin:auto;
    }
    .menu-tab{
        text-align: center;
        li{
            display: inline-block;
            width: 88px;
            line-height: 36px;
            font-size: 14px;
            color: white;
            border-radius: 2px;
            cursor: pointer;
        }
        .current{
            background-color: rgba(0,0,0,.1)
        }
    }

</style>
