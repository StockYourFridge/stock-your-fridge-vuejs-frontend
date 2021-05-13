<template>
        
    <div class="sideMenu">
        <div style="display:flex">
            <LinkButton @btn-click='changeToLogin' :decoration= "isLogin ? 'underline': 'none'" title="LOGIN" />
            <LinkButton @btn-click='changeToRegister' :decoration= "isRegister ? 'underline': 'none'" title="REGISTER" />
        </div>
        
        <Login @login="Login" v-show="isLogin"/>
        <Register v-show="isRegister"/>
        
    </div>
</template>

<script>
import Login from "./Login"
import Register from "./Register"
import LinkButton from "./LinkButton"
import Header from "./Header"

export default {
    
    name: "SideMenu",
    components: {
        Login,
        Header,
        Register,
        LinkButton
    },
    data(){
        return {
            login: true,
            register: false
        }
    },
    computed:{
        isLogin()
        {
            if(this.login === true)
                return true
            else
                return false         
        },
        isRegister()
        {
            if(this.register === true)
                return true
            else
                return false         
        },
    },
    methods:{
        changeToLogin(){
            this.login = true
            this.register = false
        },
        changeToRegister(){
            this.login = false
            this.register = true
        },
        Login(credentials)
        {
            this.$emit('login',credentials)
        }
    }

}
</script>

<style scoped>

.sideMenu {
    background: #feffe0;
    position: absolute;
    height: 97%;
    width: 30%;
    right: 0;
    margin: 10px;
}


</style>