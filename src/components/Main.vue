<template>
    <div class="main">
        <Header title = "Stock Your Fridge" />
            <div v-show = 'isNotAuthenticated' class="image">
                <img src="../assets/fridge.jpg">
            </div>

    </div>
</template>

<script>
import Header from './Header'
export default {
    name: "Main",
    components:{
        Header
    },
    computed:{
        isNotAuthenticated(){
            if(this.$route.path === '/login' || this.$route.path === '/register' || this.$route.path === '/')
            {
                return true
            }
            else
            {
                return false
            }
        },
        
    }
}
</script>

<style scoped>

.main{
    background: rgb(245, 245, 245);
    position: absolute;
    height: 97%;
    width: 68%;
    flex-direction: column;
    display: flex;
    align-items: center;
    justify-content: space-around;
    margin: 10px;
}
.image{
    height: 80%;
}
.image img{
    opacity: 0.8;
    height: 100%;
}

</style>