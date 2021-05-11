<template>
  <form class="add-form" @submit="onSubmit">
      <input type="text" v-model="username" name="username" placeholder="Enter Username" />
      <input
        type="password"
        v-model="password"
        name="password"
        placeholder="Enter Password"
      />
    <div class="buttons">
        <Button title= "LOGIN" />
    </div>
  </form>
</template>

<script>
import Button from "./Button"
export default {
  name: 'Login',
  components: {
    Button
  },
  data(){
    return {
      username: '',
      password: '',
    }
  },
  methods: {
    onSubmit(e){
      e.preventDefault()
      if(!this.username || !this.password)
      {
        alert("Enter both Username and Password")
        return
      }
      const credentials = {
        username: this.username,
        password: this.password
      } 
      this.$emit('login', credentials)

      this.username = ''
      this.password = ''

    }
  }
}
</script>

<style scoped>
.add-form{
    display: flex;
    justify-content: space-around;
    flex-direction: column;
    margin-top: 70px;
}
.add-form input{
    font-family: Poppins;
    font-size: 16px;
    font-style: normal;
    font-weight: bold;
    line-height: 24px;
    letter-spacing: 0em;
    text-align: center;
    color: black;
    background: #feffe0;
    height: 40px;
    margin: 20px;
    width: 70%;
    align-self: center;
    border: none;
    border-bottom: 3px solid black;
}
.add-form input:focus{
    outline: none;
    border-bottom: 3px solid black;
}
.buttons{
    margin-top: 30px;
    display:flex;
    justify-content: space-around;
}
</style>
