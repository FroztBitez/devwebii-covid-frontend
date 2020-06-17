<template>
  <div id="app">
    <nav class="navbar navbar-expand">
      <a href="/pacientes" class="navbar-brand btn">Pacientes Cadastro</a>      
    </nav>
    <div class="container mt-3">
      <router-view />
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  }
}
</script>

<style>
body{
  background:rgba(222, 247, 241, 0.445);
}
.navbar{
  background-color: #0f534e;
}
.navbar-brand{
  color: rgb(255, 255, 255);
  font-size: 24px;
  font-weight: bold;
  padding: 5px;
}
.navbar-brand:hover{
  background: #252e2e;
  color: rgb(255, 255, 255);
}
.table-title{
  padding-bottom: 15px;
    background: #0f534e;
    color: rgb(255, 255, 255);
    padding: 16px 60px;
    margin: -20px -25px 10px;
    border-radius: 3px 3px 0 0;
}
.table-wrapper {
    background: rgba(117, 156, 147, 0.445);
    padding: 20px 25px;
    margin: 30px 0;
    border-radius: 3px;
    box-shadow: 0 1px 1px rgba(0,0,0,.10);
    font-weight: bold;
    font-size: 25px;
}
.size{
  width: 400px;
  margin: auto;
}
</style>
