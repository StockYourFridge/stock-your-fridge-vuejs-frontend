<template>
    <button @click="onClick()">{{ title }}</button>
</template>
<script>
export default {
    name: "Button",
    props: {
        title: String,
    },
    methods:{
        onClick()
        {
            this.$emit('btn-click')
        },
    }
    
}
</script>
<style scoped>

button{
    margin-top: 20px;
    font-size: 20px;
    font-weight: bold;
    cursor: pointer;
    width: 250px;
    border: none;
    height: 40px;
    color:black;
    background: rgb(153, 253, 153);
    border-radius: 10px;
}

</style>