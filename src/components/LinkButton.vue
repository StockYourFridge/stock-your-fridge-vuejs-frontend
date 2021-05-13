<template>
    <button @click="onClick()" :style="{ background: color,'text-decoration': decoration }">{{ title }}</button>
</template>
<script>
export default {
    name: "LinkButton",
    props: {
        title: String,    
        decoration: String
        },
    methods:{
        onClick()
        {
            this.$emit('btn-click')
        },
    }
    
}
</script>
<style>

button{
    margin-top: 20px;
    font-size: 23px;
    font-weight: bold;
    cursor: pointer;
    width: 250px;
    border: none;
    height: 40px;
    color:rgb(179, 0, 250);
    background: #feffe0;
}

</style>