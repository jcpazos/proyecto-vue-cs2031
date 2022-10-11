<template>
  <img class="imagen" alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Hola Mundo!"/>
  <div class="login">
    <LoginComponent></LoginComponent>
    <!--<LogosComponent myWidth="30" myHeight="30"></LogosComponent>-->
    <TablaUsuarios></TablaUsuarios>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import LoginComponent from './components/Login.vue'
import TablaUsuarios from './components/TablaUsuarios.vue'
//import LogosComponent from './components/Logos.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    LoginComponent,
    TablaUsuarios,
    //LogosComponent
  }
}
</script>

<style>
.login {
  flex: auto;
  
}

.imagen {
  margin-left: 40%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
