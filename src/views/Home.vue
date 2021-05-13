<template>
  <div class="container">
    <SideMenu @login='Login'/>
    <Main />
  </div>
  
</template>

<script>

import SideMenu from "../components/SideMenu" 
import Main from "../components/Main"

export default {
  name: 'Home',
  components: {
    SideMenu,
    Main
  },
  methods:{
    async Login(credentials){
      const res = await fetch('http://localhost:8082/login/'+credentials.username+'/'+credentials.password, {
        method: 'GET',
        headers: {
          'Content-type': 'application/json',
        },
      })
      const data = await res.json()
      if(data === true)
      {
        this.$router.push("/")
      }

    }
  }
}

</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Poppins', sans-serif;
}

.container{
  position: absolute;
  height: 100%;
  background: rgb(229, 246, 248);
  width: 100%;

}

</style>

