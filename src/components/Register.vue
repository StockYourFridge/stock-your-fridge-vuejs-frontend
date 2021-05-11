<template>
  <form class="add-form">
      <input type="text" v-model="username" name="username" placeholder="Enter Username" />
      <input type="email" v-model="email" name="email" placeholder="Enter Email" />
      <input
        type="password"
        v-model="password"
        name="password"
        placeholder="Enter Password"
      />
      <input
        type="password"
        v-model="confirmPassword"
        name="confirmPassword"
        placeholder="Confirm Password"
      />
    <div class="buttons">
        <Button title= "REGISTER" />
    </div>
  </form>
</template>

<script>
import Button from "./Button"

export default {
  name: 'Register',
  components: {
    Button
  },
  data(){
    return {
      confirmPassword: "",
      password: "",
      username: "",
      email: ""
    }
  }

}
</script>

<style scoped>
.add-form{
    margin-top: 30px;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
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
