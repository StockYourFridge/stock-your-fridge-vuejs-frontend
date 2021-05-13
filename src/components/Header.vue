<template>
  <header>
    <h1>{{ title }}</h1>

  </header>
</template>

<script>

export default {
  name: 'Header',
  props: {
    title: String,
    showAddTask: Boolean,
  },
}
</script>

<style scoped>
header {
    font-size: 18px;
    color: #C85BB0;   
    margin-top: 20px;
    display: flex;
    justify-content: space-around;
    align-items: center;
    margin-bottom: 20px;
}
</style>
